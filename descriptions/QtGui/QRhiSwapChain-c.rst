.. sip:class-description::
    :status: todo
    :brief: Swapchain resource
    :digest: c6c6b5dffda7e16c7c9ccd400ac24aa2

Swapchain resource.

A swapchain enables presenting rendering results to a surface. A swapchain is typically backed by a set of color buffers. Of these, one is displayed at a time.

Below is a typical pattern for creating and managing a swapchain and some associated resources in order to render onto a :sip:ref:`~PyQt6.QtGui.QWindow`:

::

    void init()
    {
        sc = rhi->newSwapChain();
        ds = rhi->newRenderBuffer(QRhiRenderBuffer::DepthStencil,
                                  QSize(), // no need to set the size here due to UsedWithSwapChainOnly
                                  1,
                                  QRhiRenderBuffer::UsedWithSwapChainOnly);
        sc->setWindow(window);
        sc->setDepthStencil(ds);
        rp = sc->newCompatibleRenderPassDescriptor();
        sc->setRenderPassDescriptor(rp);
        resizeSwapChain();
    }

    void resizeSwapChain()
    {
        hasSwapChain = sc->createOrResize();
    }

    void render()
    {
        if (!hasSwapChain || notExposed)
            return;

        if (sc->currentPixelSize() != sc->surfacePixelSize() || newlyExposed) {
            resizeSwapChain();
            if (!hasSwapChain)
                return;
            newlyExposed = false;
        }

        rhi->beginFrame(sc);
        // ...
        rhi->endFrame(sc);
    }

Avoid relying on :sip:ref:`~PyQt6.QtGui.QWindow` resize events to resize swapchains, especially considering that surface sizes may not always fully match the :sip:ref:`~PyQt6.QtGui.QWindow` reported dimensions. The safe, cross-platform approach is to do the check via surfacePixelSize() whenever starting a new frame.

Releasing the swapchain must happen while the :sip:ref:`~PyQt6.QtGui.QWindow` and the underlying native window is fully up and running. Building on the previous example:

::

    void releaseSwapChain()
    {
        if (hasSwapChain) {
            sc->destroy();
            hasSwapChain = false;
        }
    }

    // assuming Window is our QWindow subclass
    bool Window::event(QEvent *e)
    {
        switch (e->type()) {
        case QEvent::UpdateRequest: // for QWindow::requestUpdate()
            render();
            break;
        case QEvent::PlatformSurface:
            if (static_cast<QPlatformSurfaceEvent *>(e)->surfaceEventType() == QPlatformSurfaceEvent::SurfaceAboutToBeDestroyed)
                releaseSwapChain();
            break;
        default:
            break;
        }
        return QWindow::event(e);
    }

Initializing the swapchain and starting to render the first frame cannot start at any time. The safe, cross-platform approach is to rely on expose events. :sip:ref:`~PyQt6.QtGui.QExposeEvent` is a loosely specified event that is sent whenever a window gets mapped, obscured, and resized, depending on the platform.

::

    void Window::exposeEvent(QExposeEvent *)
    {
        // initialize and start rendering when the window becomes usable for graphics purposes
        if (isExposed() && !running) {
            running = true;
            init();
        }

        // stop pushing frames when not exposed or size becomes 0
        if ((!isExposed() || (hasSwapChain && sc->surfacePixelSize().isEmpty())) && running)
            notExposed = true;

        // continue when exposed again and the surface has a valid size
        if (isExposed() && running && notExposed && !sc->surfacePixelSize().isEmpty()) {
            notExposed = false;
            newlyExposed = true;
        }

        if (isExposed() && !sc->surfacePixelSize().isEmpty())
            render();
    }

Once the rendering has started, a simple way to request a new frame is :sip:ref:`~PyQt6.QtGui.QWindow.requestUpdate`. While on some platforms this is merely a small timer, on others it has a specific implementation: for instance on macOS or iOS it may be backed by `CVDisplayLink <https://developer.apple.com/documentation/corevideo/cvdisplaylink?language=objc>`_. The example above is already prepared for update requests by handling :sip:ref:`~PyQt6.QtCore.QEvent.Type.UpdateRequest`.

While acting as a :sip:ref:`~PyQt6.QtGui.QRhiRenderTarget`, :sip:ref:`~PyQt6.QtGui.QRhiSwapChain` also manages a :sip:ref:`~PyQt6.QtGui.QRhiCommandBuffer`. Calling :sip:ref:`~PyQt6.QtGui.QRhi.endFrame` submits the recorded commands and also enqueues a ``present`` request. The default behavior is to do this with a swap interval of 1, meaning synchronizing to the display's vertical refresh is enabled. Thus the rendering thread calling beginFrame() and endFrame() will get throttled to vsync. On some backends this can be disabled by passing :sip:ref:`~PyQt6.QtGui.QRhiSwapChain`:\ :sip:ref:`~PyQt6.QtGui.QRhiSwapChain.Flag.NoVSync` in flags().

Multisampling (MSAA) is handled transparently to the applications when requested via setSampleCount(). Where applicable, :sip:ref:`~PyQt6.QtGui.QRhiSwapChain` will take care of creating additional color buffers and issuing a multisample resolve command at the end of a frame. For OpenGL, it is necessary to request the appropriate sample count also via :sip:ref:`~PyQt6.QtGui.QSurfaceFormat`, by calling :sip:ref:`~PyQt6.QtGui.QSurfaceFormat.setDefaultFormat` before initializing the :sip:ref:`~PyQt6.QtGui.QRhi`.

**Note:** This is a RHI API with limited compatibility guarantees, see :sip:ref:`~PyQt6.QtGui.QRhi` for details.
