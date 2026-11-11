.. sip:class-description::
    :status: todo
    :brief: Accelerated 2D/3D graphics API abstraction
    :digest: 687d4f0eba5123816d41f833ce96b8f9

Accelerated 2D/3D graphics API abstraction.

The Qt Rendering Hardware Interface is an abstraction for hardware accelerated graphics APIs, such as, `OpenGL <https://www.khronos.org/opengl/>`_, `OpenGL ES <https://www.khronos.org/opengles/>`_, `Direct3D <https://docs.microsoft.com/en-us/windows/desktop/direct3d>`_, `Metal <https://developer.apple.com/metal/>`_, and `Vulkan <https://www.khronos.org/vulkan/>`_.

**Warning:** The :sip:ref:`~PyQt6.QtGui.QRhi` family of classes in the Qt Gui module, including :sip:ref:`~PyQt6.QtGui.QShader` and :sip:ref:`~PyQt6.QtGui.QShaderDescription`, offer limited compatibility guarantees. There are no source or binary compatibility guarantees for these classes, meaning the API is only guaranteed to work with the Qt version the application was developed against. Source incompatible changes are however aimed to be kept at a minimum and will only be made in minor releases (6.7, 6.8, and so on). To use these classes in an application, link to ``Qt::GuiPrivate`` (if using CMake), and include the headers with the ``rhi`` prefix, for example ``#include <rhi/qrhi.h>``.

Each :sip:ref:`~PyQt6.QtGui.QRhi` instance is backed by a backend for a specific graphics API. The selection of the backend is a run time choice and is up to the application or library that creates the :sip:ref:`~PyQt6.QtGui.QRhi` instance. Some backends are available on multiple platforms (OpenGL, Vulkan, Null), while APIs specific to a given platform are only available when running on the platform in question (Metal on macOS/iOS, Direct3D on Windows).

The available backends currently are:

* OpenGL 2.1 / OpenGL ES 2.0 or newer. Some extensions and newer core specification features are utilized when present, for example to enable multisample framebuffers or compute shaders. Operating in core profile contexts is supported as well. If necessary, applications can query the :sip:ref:`~PyQt6.QtGui.QRhi.Feature` at runtime to check for features that are not supported in the OpenGL context backing the :sip:ref:`~PyQt6.QtGui.QRhi`. The OpenGL backend builds on :sip:ref:`~PyQt6.QtGui.QOpenGLContext`, QOpenGLFunctions, and the related cross-platform infrastructure of the Qt GUI module.

* Direct3D 11.2 and newer (with DXGI 1.3 and newer), using Shader Model 5.0 or newer. When the D3D runtime has no support for 11.2 features or Shader Model 5.0, initialization using an accelerated graphics device will fail, but using the `software adapter <https://learn.microsoft.com/en-us/windows/win32/direct3darticles/directx-warp>`_ is still an option.

* Direct3D 12 on Windows 10 version 1703 and newer, with Shader Model 5.0 or newer. Qt requires ID3D12Device2 to be present, hence the requirement for at least version 1703 of Windows 10. The D3D12 device is by default created with specifying a minimum feature level of ``D3D_FEATURE_LEVEL_11_0``.

* Metal 1.2 or newer.

* Vulkan 1.0 or newer, optionally utilizing some Vulkan 1.1 level features.

* Null, a "dummy" backend that issues no graphics calls at all.

In order to allow shader code to be written once in Qt applications and libraries, all shaders are expected to be written in a single language which is then compiled into SPIR-V. Versions for various shading language are then generated from that, together with reflection information (inputs, outputs, shader resources). This is then packed into easily and efficiently serializable :sip:ref:`~PyQt6.QtGui.QShader` instances. The compilers and tools to generate such shaders are not part of :sip:ref:`~PyQt6.QtGui.QRhi` and the Qt GUI module, but the core classes for using such shaders, :sip:ref:`~PyQt6.QtGui.QShader` and :sip:ref:`~PyQt6.QtGui.QShaderDescription`, are. The APIs and tools for performing compilation and translation are part of the Qt Shader Tools module.

See the `RHI Window Example <https://doc.qt.io/qt-6/qtgui-rhiwindow-example.html>`_ for an introductory example of creating a portable, cross-platform application that performs accelerated 3D rendering onto a :sip:ref:`~PyQt6.QtGui.QWindow` using :sip:ref:`~PyQt6.QtGui.QRhi`.

.. _qrhi-an-impression-of-the-api:

An Impression of the API
------------------------

To provide a quick look at the API with a short yet complete example that does not involve window-related setup, the following is a complete, runnable cross-platform application that renders 20 frames off-screen, and then saves the generated images to files after reading back the texture contents from the GPU. For an example that renders on-screen, which then involves setting up a :sip:ref:`~PyQt6.QtGui.QWindow` and a swapchain, refer to the `RHI Window Example <https://doc.qt.io/qt-6/qtgui-rhiwindow-example.html>`_.

For brevity, the initialization of the :sip:ref:`~PyQt6.QtGui.QRhi` is done based on the platform: the sample code here chooses Direct 3D 12 on Windows, Metal on macOS and iOS, and Vulkan otherwise. OpenGL and Direct 3D 11 are never used by this application, but support for those could be introduced with a few additional lines.

.. literalinclude:: ../../../snippets/qtbase-src-gui-doc-snippets-rhioffscreen-main.py
    :lines: 7-152

The result of the application is 20 ``PNG`` images (frame0.png - frame19.png). These contain a rotating triangle with varying opacity over a green background.

The vertex and fragment shaders are expected to be processed and packaged into ``.qsb`` files. The Vulkan-compatible GLSL source code is the following:

*color.vert*

.. literalinclude:: ../../../snippets/qtbase-src-gui-doc-snippets-rhioffscreen-color.vert
    :lines: 4-19

*color.frag*

.. literalinclude:: ../../../snippets/qtbase-src-gui-doc-snippets-rhioffscreen-color.frag
    :lines: 4-17

To manually compile and transpile these shaders to a number of targets (SPIR-V, HLSL, MSL, GLSL) and generate the ``.qsb`` files the application loads at run time, run ``qsb --qt6 color.vert -o color.vert.qsb`` and ``qsb --qt6 color.frag -o color.frag.qsb``. Alternatively, the Qt Shader Tools module offers build system integration for CMake, the ``qt_add_shaders()`` CMake function, that can achieve the same at build time.

.. _qrhi-security-considerations:

Security Considerations
-----------------------

All data consumed by :sip:ref:`~PyQt6.QtGui.QRhi` and related classes such as :sip:ref:`~PyQt6.QtGui.QShader` are considered trusted content.

**Warning:** Application developers are advised to carefully consider the potential implications before allowing the feeding of user-provided content that is not part of the application and is not under the developers' control. (this includes all vertex/index data, shaders, pipeline and draw call parameters, etc.)

.. _qrhi-design-fundamentals:

Design Fundamentals
-------------------

A :sip:ref:`~PyQt6.QtGui.QRhi` cannot be instantiated directly. Instead, use the :sip:ref:`~PyQt6.QtGui.QRhi.create` function. Delete the :sip:ref:`~PyQt6.QtGui.QRhi` instance normally to release the graphics device.

.. _qrhi-resources:

Resources
.........

Instances of classes deriving from :sip:ref:`~PyQt6.QtGui.QRhiResource`, such as, :sip:ref:`~PyQt6.QtGui.QRhiBuffer`, :sip:ref:`~PyQt6.QtGui.QRhiTexture`, etc., encapsulate zero, one, or more native graphics resources. Instances of such classes are always created via the ``new`` functions of the :sip:ref:`~PyQt6.QtGui.QRhi`, such as, :sip:ref:`~PyQt6.QtGui.QRhi.newBuffer`, :sip:ref:`~PyQt6.QtGui.QRhi.newTexture`, :sip:ref:`~PyQt6.QtGui.QRhi.newTextureRenderTarget`, :sip:ref:`~PyQt6.QtGui.QRhi.newSwapChain`.

::

    QRhiBuffer *vbuf = rhi->newBuffer(QRhiBuffer::Immutable, QRhiBuffer::VertexBuffer, sizeof(vertexData));
    if (!vbuf->create()) { error(); }
    // ...
    delete vbuf;

* The returned value from functions like :sip:ref:`~PyQt6.QtGui.QRhi.newBuffer` is always owned by the caller.

* Just creating an instance of a :sip:ref:`~PyQt6.QtGui.QRhiResource` subclass never allocates or initializes any native resources. That is only done when calling the ``create()`` function of a subclass, for example, QRhiBuffer::create() or QRhiTexture::create().

* The exceptions are QRhiTextureRenderTarget::newCompatibleRenderPassDescriptor(), QRhiSwapChain::newCompatibleRenderPassDescriptor(), and QRhiRenderPassDescriptor::newCompatibleRenderPassDescriptor(). There is no ``create()`` operation for these and the returned object is immediately active.

* The resource objects themselves are treated as immutable: once a resource has :sip:ref:`~PyQt6.QtGui.QRhi.create` called, changing any parameters via the setters, such as, QRhiTexture::setPixelSize(), has no effect, unless the underlying native resource is released and ``create()`` is called again. See more about resource reuse in the sections below.

* The underlying native resources are scheduled for releasing by the :sip:ref:`~PyQt6.QtGui.QRhiResource` destructor, or by calling QRhiResource::destroy(). Backends often queue release requests and defer executing them to an unspecified time, this is hidden from the applications. This way applications do not have to worry about releasing native resources that may still be in use by an in-flight frame.

* Note that this does not mean that a :sip:ref:`~PyQt6.QtGui.QRhiResource` can freely be destroy()'ed or deleted within a frame (that is, in a :sip:ref:`~PyQt6.QtGui.QRhi.beginFrame` - :sip:ref:`~PyQt6.QtGui.QRhi.endFrame` section). As a general rule, all referenced :sip:ref:`~PyQt6.QtGui.QRhiResource` objects must stay unchanged until the frame is submitted by calling :sip:ref:`~PyQt6.QtGui.QRhi.endFrame`. To ease this, :sip:ref:`~PyQt6.QtGui.QRhiResource.deleteLater` is provided as a convenience.

.. _qrhi-command-buffers-and-deferred-command-execution:

Command buffers and deferred command execution
..............................................

Regardless of the design and capabilities of the underlying graphics API, all :sip:ref:`~PyQt6.QtGui.QRhi` backends implement some level of command buffers. No :sip:ref:`~PyQt6.QtGui.QRhiCommandBuffer` function issues any native bind or draw command (such as, ``glDrawElements``) directly. Commands are always recorded in a queue, either native or provided by the :sip:ref:`~PyQt6.QtGui.QRhi` backend. The command buffer is submitted, and so execution starts only upon :sip:ref:`~PyQt6.QtGui.QRhi.endFrame` or :sip:ref:`~PyQt6.QtGui.QRhi.finish`.

The deferred nature has consequences for some types of objects. For example, writing to a dynamic buffer multiple times within a frame, in case such buffers are backed by host-visible memory, will result in making the results of all writes are visible to all draw calls in the command buffer of the frame, regardless of when the dynamic buffer update was recorded relative to a draw call.

Furthermore, instances of :sip:ref:`~PyQt6.QtGui.QRhiResource` subclasses must be treated immutable within a frame in which they are referenced in any way. Create all resources upfront, before starting to record commands for the next frame. Reusing a :sip:ref:`~PyQt6.QtGui.QRhiResource` instance within a frame (by calling ``create()`` then referencing it again in the same ``beginFrame - endFrame`` section) should be avoided as it may lead to unexpected results, depending on the backend.

As a general rule, all referenced :sip:ref:`~PyQt6.QtGui.QRhiResource` objects must stay valid and unmodified until the frame is submitted by calling :sip:ref:`~PyQt6.QtGui.QRhi.endFrame`. On the other hand, calling destroy() or deleting the :sip:ref:`~PyQt6.QtGui.QRhiResource` are always safe once the frame is submitted, regardless of the status of the underlying native resources (which may still be in use by the GPU - but that is taken care of internally).

Unlike APIs like OpenGL, upload and copy type of commands cannot be mixed with draw commands. The typical renderer will involve a sequence similar to the following:

* (re)create resources

* begin frame

* record/issue uploads and copies

* start recording a render pass

* record draw calls

* end render pass

* end frame

Recording copy type of operations happens via :sip:ref:`~PyQt6.QtGui.QRhiResourceUpdateBatch`. Such operations are committed typically on :sip:ref:`~PyQt6.QtGui.QRhiCommandBuffer.beginPass`.

When working with legacy rendering engines designed for OpenGL, the migration to :sip:ref:`~PyQt6.QtGui.QRhi` often involves redesigning from having a single ``render`` step (that performs copies and uploads, clears buffers, and issues draw calls, all mixed together) to a clearly separated, two phase ``prepare`` - ``render`` setup where the ``render`` step only starts a renderpass and records draw calls, while all resource creation and queuing of updates, uploads and copies happens beforehand, in the ``prepare`` step.

:sip:ref:`~PyQt6.QtGui.QRhi` does not at the moment allow freely creating and submitting command buffers. This may be lifted in the future to some extent, in particular if compute support is introduced, but the model of well defined ``frame-start`` and ``frame-end`` points, combined with a dedicated, "frame" command buffer, where ``frame-end`` implies presenting, is going to remain the primary way of operating since this is what fits Qt's various UI technologies best.

.. _qrhi-threading:

Threading
.........

A :sip:ref:`~PyQt6.QtGui.QRhi` instance and the associated resources can be created and used on any thread but all usage must be limited to that one single thread. When rendering to multiple QWindows in an application, having a dedicated thread and :sip:ref:`~PyQt6.QtGui.QRhi` instance for each window is often advisable, as this can eliminate issues with unexpected throttling caused by presenting to multiple windows. Conceptually that is then the same as how Qt Quick scene graph's threaded render loop operates when working directly with OpenGL: one thread for each window, one :sip:ref:`~PyQt6.QtGui.QOpenGLContext` for each thread. When moving onto :sip:ref:`~PyQt6.QtGui.QRhi`, :sip:ref:`~PyQt6.QtGui.QOpenGLContext` is replaced by :sip:ref:`~PyQt6.QtGui.QRhi`, making the migration straightforward.

When it comes to externally created native objects, such as OpenGL contexts passed in via :sip:ref:`~PyQt6.QtGui.QRhiGles2NativeHandles`, it is up to the application to ensure they are not misused by other threads.

Resources are not shareable between :sip:ref:`~PyQt6.QtGui.QRhi` instances. This is an intentional choice since :sip:ref:`~PyQt6.QtGui.QRhi` hides most queue, command buffer, and resource synchronization related tasks, and provides no API for them. Safe and efficient concurrent use of graphics resources from multiple threads is tied to those concepts, however, and is thus a topic that is currently out of scope, but may be introduced in the future.

**Note:** The Metal backend requires that an autorelease pool is available on the rendering thread, ideally wrapping each iteration of the render loop. This needs no action from the users of :sip:ref:`~PyQt6.QtGui.QRhi` when rendering on the main (gui) thread, but becomes important when a separate, dedicated render thread is used.

.. _qrhi-resource-synchronization:

Resource synchronization
........................

:sip:ref:`~PyQt6.QtGui.QRhi` does not expose APIs for resource barriers or image layout transitions. Such synchronization is done implicitly by the backends, where applicable (for example, Vulkan), by tracking resource usage as necessary. Buffer and image barriers are inserted before render or compute passes transparently to the application.

**Note:** Resources within a render or compute pass are expected to be bound to a single usage during that pass. For example, a buffer can be used as vertex, index, uniform, or storage buffer, but not a combination of them within a single pass. However, it is perfectly fine to use a buffer as a storage buffer in a compute pass, and then as a vertex buffer in a render pass, for example, assuming the buffer declared both usages upon creation.

**Note:** Textures have this rule relaxed in certain cases, because using two subresources (typically two different mip levels) of the same texture for different access (one for load, one for store) is supported even within the same pass.

.. _qrhi-resource-reuse:

Resource reuse
..............

From the user's point of view a :sip:ref:`~PyQt6.QtGui.QRhiResource` is reusable immediately after calling QRhiResource::destroy(). With the exception of swapchains, calling ``create()`` on an already created object does an implicit ``destroy()``. This provides a handy shortcut to reuse a :sip:ref:`~PyQt6.QtGui.QRhiResource` instance with different parameters, with a new native graphics object underneath.

The importance of reusing the same object lies in the fact that some objects reference other objects: for example, a :sip:ref:`~PyQt6.QtGui.QRhiShaderResourceBindings` can reference :sip:ref:`~PyQt6.QtGui.QRhiBuffer`, :sip:ref:`~PyQt6.QtGui.QRhiTexture`, and :sip:ref:`~PyQt6.QtGui.QRhiSampler` instances. If in a later frame one of these buffers need to be resized or a sampler parameter needs changing, destroying and creating a whole new :sip:ref:`~PyQt6.QtGui.QRhiBuffer` or :sip:ref:`~PyQt6.QtGui.QRhiSampler` would invalidate all references to the old instance. By just changing the appropriate parameters via QRhiBuffer::setSize() or similar and then calling QRhiBuffer::create(), everything works as expected and there is no need to touch the :sip:ref:`~PyQt6.QtGui.QRhiShaderResourceBindings` at all, even though there is a good chance that under the hood the :sip:ref:`~PyQt6.QtGui.QRhiBuffer` is now backed by a whole new native buffer.

::

    QRhiBuffer *ubuf = rhi->newBuffer(QRhiBuffer::Dynamic, QRhiBuffer::UniformBuffer, 256);
    ubuf->create();

    QRhiShaderResourceBindings *srb = rhi->newShaderResourceBindings()
    srb->setBindings({
        QRhiShaderResourceBinding::uniformBuffer(0, QRhiShaderResourceBinding::VertexStage | QRhiShaderResourceBinding::FragmentStage, ubuf)
    });
    srb->create();

    // ...

    // now in a later frame we need to grow the buffer to a larger size
    ubuf->setSize(512);
    ubuf->create(); // same as ubuf->destroy(); ubuf->create();

    // srb needs no changes whatsoever, any references in it to ubuf
    // stay valid. When it comes to internal details, such as that
    // ubuf may now be backed by a completely different native buffer
    // resource, that is is recognized and handled automatically by the
    // next setShaderResources().

:sip:ref:`~PyQt6.QtGui.QRhiTextureRenderTarget` offers the same contract: calling :sip:ref:`~PyQt6.QtGui.QRhiCommandBuffer.beginPass` is safe even when one of the render target's associated textures or renderbuffers has been rebuilt (by calling ``create()`` on it) since the creation of the render target object. This allows the application to resize a texture by setting a new pixel size on the :sip:ref:`~PyQt6.QtGui.QRhiTexture` and calling :sip:ref:`~PyQt6.QtGui.QRhi.create`, thus creating a whole new native texture resource underneath, without having to update the :sip:ref:`~PyQt6.QtGui.QRhiTextureRenderTarget` as that will be done implicitly in beginPass().

.. _qrhi-pooled-objects:

Pooled objects
..............

In addition to resources, there are pooled objects as well, such as, :sip:ref:`~PyQt6.QtGui.QRhiResourceUpdateBatch`. An instance is retrieved via a ``next`` function, such as, :sip:ref:`~PyQt6.QtGui.QRhi.nextResourceUpdateBatch`. The caller does not own the returned instance in this case. The only valid way of operating here is calling functions on the :sip:ref:`~PyQt6.QtGui.QRhiResourceUpdateBatch` and then passing it to :sip:ref:`~PyQt6.QtGui.QRhiCommandBuffer.beginPass` or :sip:ref:`~PyQt6.QtGui.QRhiCommandBuffer.endPass`. These functions take care of returning the batch to the pool. Alternatively, a batch can be "canceled" and returned to the pool without processing by calling :sip:ref:`~PyQt6.QtGui.QRhiResourceUpdateBatch.release`.

A typical pattern is thus:

::

    QRhiResourceUpdateBatch *resUpdates = rhi->nextResourceUpdateBatch();
    // ...
    resUpdates->updateDynamicBuffer(ubuf, 0, 64, mvp.constData());
    if (!image.isNull()) {
        resUpdates->uploadTexture(texture, image);
        image = QImage();
    }
    // ...
    QRhiCommandBuffer *cb = m_sc->currentFrameCommandBuffer();
    // note the last argument
    cb->beginPass(swapchain->currentFrameRenderTarget(), clearCol, clearDs, resUpdates);

.. _qrhi-swapchain-specifics:

Swapchain specifics
...................

:sip:ref:`~PyQt6.QtGui.QRhiSwapChain` features some special semantics due to the peculiar nature of swapchains.

* It has no ``create()`` but rather a QRhiSwapChain::createOrResize(). Repeatedly calling this function is **not** the same as calling QRhiSwapChain::destroy() followed by QRhiSwapChain::createOrResize(). This is because swapchains often have ways to handle the case where buffers need to be resized in a manner that is more efficient than a brute force destroying and recreating from scratch.

* An active :sip:ref:`~PyQt6.QtGui.QRhiSwapChain` must be released by calling destroy(), or by destroying the object, before the :sip:ref:`~PyQt6.QtGui.QWindow`'s underlying QPlatformWindow, and so the associated native window object, is destroyed. It should not be postponed because releasing the swapchain may become problematic (and with some APIs, like Vulkan, is explicitly disallowed) when the native window is not around anymore, for example because the QPlatformWindow got destroyed upon getting a :sip:ref:`~PyQt6.QtGui.QWindow.close`. Therefore, releasing the swapchain must happen whenever the targeted :sip:ref:`~PyQt6.QtGui.QWindow` sends the :sip:ref:`~PyQt6.QtGui.QPlatformSurfaceEvent.SurfaceEventType.SurfaceAboutToBeDestroyed` event. If the event does not arrive before the destruction of the :sip:ref:`~PyQt6.QtGui.QWindow` - this can happen when using :sip:ref:`~PyQt6.QtCore.QCoreApplication.quit` -, then check QWindow::handle() after the event loop exits and invoke the swapchain release when non-null (meaning the underlying native window is still around).

.. _qrhi-ownership:

Ownership
.........

The general rule is no ownership transfer. Creating a :sip:ref:`~PyQt6.QtGui.QRhi` with an already existing graphics device does not mean the :sip:ref:`~PyQt6.QtGui.QRhi` takes ownership of the device object. Similarly, ownership is not given away when a device or texture object is "exported" via :sip:ref:`~PyQt6.QtGui.QRhi.nativeHandles` or :sip:ref:`~PyQt6.QtGui.QRhiTexture.nativeTexture`. Most importantly, passing pointers in structs and via setters does not transfer ownership.

.. _qrhi-troubleshooting-and-profiling:

Troubleshooting and Profiling
-----------------------------

.. _qrhi-error-reporting:

Error reporting
...............

Functions such as :sip:ref:`~PyQt6.QtGui.QRhi.create` and the resource classes' ``create()`` member functions (e.g., QRhiBuffer::create()) indicate failure with the return value (``nullptr`` or ``false``, respectively). When working with :sip:ref:`~PyQt6.QtGui.QShader`, :sip:ref:`~PyQt6.QtGui.QShader.fromSerialized` returns an invalid :sip:ref:`~PyQt6.QtGui.QShader` (for which :sip:ref:`~PyQt6.QtGui.QShader.isValid` returns ``false``) when the data passed to the function cannot be successfully deserialized. Some functions, :sip:ref:`~PyQt6.QtGui.QRhi.beginFrame` in particular, may also sometimes report "soft failures", such as :sip:ref:`~PyQt6.QtGui.QRhi.FrameOpResult.FrameOpSwapChainOutOfDate`, which do not indicate an unrecoverable error, but rather should be seen as a "try again later" response.

Warnings and errors may get printed at any time to the debug output via :sip:ref:`~PyQt6.QtCore.qWarning`. It is therefore always advisable to inspect the output of the application.

Additional debug messages can be enabled via the following logging categories. Messages from these categories are not printed by default unless explicitly enabled via :sip:ref:`~PyQt6.QtCore.QLoggingCategory` or the ``QT_LOGGING_RULES`` environment variable. For better interoperation with Qt Quick, the environment variable ``QSG_INFO`` also enables these debug prints.

* ``qt.rhi.general``

Additionally, applications can query the :sip:ref:`~PyQt6.QtGui.QRhi.backendName` and :sip:ref:`~PyQt6.QtGui.QRhi.driverInfo` from a successfully initialized :sip:ref:`~PyQt6.QtGui.QRhi`. This can then be printed to the user or stored in the application logs even in production builds, if desired.

.. _qrhi-investigating-rendering-problems:

Investigating rendering problems
................................

When the rendering results are not as expected, or the application is experiencing problems, always consider checking with the native 3D APIs' debug and validation facilities. :sip:ref:`~PyQt6.QtGui.QRhi` itself features limited error checking since replicating the already existing, vast amount of functionality in the underlying layers is not reasonable.

* For Vulkan, controlling the `Vulkan Validation Layers <https://github.com/KhronosGroup/Vulkan-ValidationLayers>`_ is not in the scope of the :sip:ref:`~PyQt6.QtGui.QRhi`, but rather can be achieved by configuring the :sip:ref:`~PyQt6.QtGui.QVulkanInstance` with the appropriate layers. For example, call ``instance.setLayers({ "VK_LAYER_KHRONOS_validation" });`` before invoking :sip:ref:`~PyQt6.QtGui.QVulkanInstance.create` on the :sip:ref:`~PyQt6.QtGui.QVulkanInstance`. (note that this assumes that the validation layers are actually installed and available, e.g. from the Vulkan SDK) By default, :sip:ref:`~PyQt6.QtGui.QVulkanInstance` conveniently redirects the Vulkan debug messages to :sip:ref:`~PyQt6.QtCore.qDebug`, meaning the validation messages get printed just like other Qt warnings.

* With Direct 3D 11 and 12, a graphics device with the debug layer enabled can be requested by toggling the ``enableDebugLayer`` flag in the appropriate :sip:ref:`~PyQt6.QtGui.QRhiD3D11InitParams`. With Direct 3D 12 the messages are then printed via :sip:ref:`~PyQt6.QtCore.qDebug`, just like the Vulkan validation messages, as long as the debug layer supports message callbacks. Otherwise, and always with Direct 3D 11, the messages appear on the debug output, which is visible in Qt Creator's messages panel or via a tool such as `DebugView <https://learn.microsoft.com/en-us/sysinternals/downloads/debugview>`_.

* For Metal, controlling Metal Validation is outside of :sip:ref:`~PyQt6.QtGui.QRhi`'s scope. Rather, to enable validation, run the application with the environment variable ``METAL_DEVICE_WRAPPER_TYPE=1`` set, or run the application within XCode. There may also be further settings and environment variable in modern XCode and macOS versions. See for instance `this page <https://developer.apple.com/documentation/metal/diagnosing_metal_programming_issues_early>`_.

.. _qrhi-frame-captures-and-performance-profiling:

Frame captures and performance profiling
........................................

A Qt application rendering with :sip:ref:`~PyQt6.QtGui.QRhi` to a window while relying on a 3D API under the hood, is, from the windowing and graphics pipeline perspective at least, no different from any other (non-Qt) applications using the same 3D API. This means that tools and practices for debugging and profiling applications involving 3D graphics, such as games, all apply to such a Qt application as well.

A few examples of tools that can provide insights into the rendering internals of Qt applications that use :sip:ref:`~PyQt6.QtGui.QRhi`, which includes Qt Quick and Qt Quick 3D based projects as well:

* `RenderDoc <https://renderdoc.org/>`_ allows taking frame captures and introspecting the recorded commands and pipeline state on Windows and Linux for applications using OpenGL, Vulkan, D3D11, or D3D12. When trying to figure out why some parts of the 3D scene do not show up as expected, RenderDoc is often a fast and efficient way to check the pipeline stages and the related state and discover the missing or incorrect value. It is also a tool that is actively used when developing Qt itself.

* For NVIDIA-based systems, `Nsight Graphics <https://developer.nvidia.com/nsight-graphics>`_ provides a graphics debugger tool on Windows and Linux. In addition to investigating the commands in the frame and the pipeline, the vendor-specific tools allow looking at timings and hardware performance information, which is not something simple frame captures can provide.

* For AMD-based systems, the `Radeon GPU Profiler <https://gpuopen.com/rgp/>`_ can be used to gain deeper insights into the application's rendering and its performance.

* Overlays showing live performance information can be highly useful as well, and are often preferable to implementing simple frames-per-second counters within the application itself, since they are more reliable and show more information. An example is `PresentMon <https://game.intel.com/us/intel-presentmon/>`_, which supports graphics hardware from multiple vendors.

* As :sip:ref:`~PyQt6.QtGui.QRhi` supports Direct 3D 12, using `PIX <https://devblogs.microsoft.com/pix/download/>`_, a performance tuning and debugging tool for DirectX 12 games on Windows is an option as well.

* On macOS, `the XCode Metal debugger <https://developer.apple.com/documentation/metal/debugging_tools/viewing_your_gpu_workload_with_the_metal_debugger>`_ can be used to take and introspect frame captures, to investigate performance details, and debug shaders. In macOS 13 it is also possible to enable an overlay that displays frame rate and other information for any Metal-based window by setting the environment variable ``MTL_HUD_ENABLED=1``.

On mobile and embedded platforms, there may be vendor and platform-specific tools, provided by the GPU or SoC vendor, available to perform performance profiling of application using OpenGL ES or Vulkan.

When capturing frames, remember that objects and groups of commands can be named via debug markers, as long as :sip:ref:`~PyQt6.QtGui.QRhi.Flag.EnableDebugMarkers` for the :sip:ref:`~PyQt6.QtGui.QRhi`, and the graphics API in use supports this. To annotate the command stream, call :sip:ref:`~PyQt6.QtGui.QRhiCommandBuffer.debugMarkBegin`, :sip:ref:`~PyQt6.QtGui.QRhiCommandBuffer.debugMarkEnd` and/or :sip:ref:`~PyQt6.QtGui.QRhiCommandBuffer.debugMarkMsg`. This can be particularly useful in larger frames with multiple render passes. Resources are named by calling :sip:ref:`~PyQt6.QtGui.QRhiResource.setName` before :sip:ref:`~PyQt6.QtGui.QRhi.create`.

To perform basic timing measurements on the CPU and GPU side within the application, :sip:ref:`~PyQt6.QtCore.QElapsedTimer` and :sip:ref:`~PyQt6.QtGui.QRhiCommandBuffer.lastCompletedGpuTime` can be used. The latter is only available with select graphics APIs at the moment and requires opting in via the :sip:ref:`~PyQt6.QtGui.QRhi.Flag.EnableTimestamps` flag.

.. _qrhi-resource-leak-checking:

Resource leak checking
......................

When destroying a :sip:ref:`~PyQt6.QtGui.QRhi` object without properly destroying all buffers, textures, and other resources created from it, warnings about this are printed to the debug output whenever the application is a debug build, or when the ``QT_RHI_LEAK_CHECK`` environment variable is set to a non-zero value. This is a simple way to discover design issues around resource handling within the application rendering logic. Note however that some platforms and underlying graphics APIs may perform their own allocation and resource leak detection as well, over which Qt will have no direct control. For example, when using Vulkan, the memory allocator may raise failing assertions in debug builds when resources that own graphics memory allocations are not destroyed before the :sip:ref:`~PyQt6.QtGui.QRhi`. In addition, the Vulkan validation layer, when enabled, will issue warnings about native graphics resources that were not released. Similarly, with Direct 3D warnings may get printed about unreleased COM objects when the application does not destroy the :sip:ref:`~PyQt6.QtGui.QRhi` and its resources in the correct order.

.. seealso:: `RHI Window Example <https://doc.qt.io/qt-6/qtgui-rhiwindow-example.html>`_, :sip:ref:`~PyQt6.QtGui.QRhiCommandBuffer`, :sip:ref:`~PyQt6.QtGui.QRhiResourceUpdateBatch`, :sip:ref:`~PyQt6.QtGui.QRhiShaderResourceBindings`, :sip:ref:`~PyQt6.QtGui.QShader`, :sip:ref:`~PyQt6.QtGui.QRhiBuffer`, :sip:ref:`~PyQt6.QtGui.QRhiTexture`, :sip:ref:`~PyQt6.QtGui.QRhiRenderBuffer`, :sip:ref:`~PyQt6.QtGui.QRhiSampler`, :sip:ref:`~PyQt6.QtGui.QRhiTextureRenderTarget`, :sip:ref:`~PyQt6.QtGui.QRhiGraphicsPipeline`, :sip:ref:`~PyQt6.QtGui.QRhiComputePipeline`, :sip:ref:`~PyQt6.QtGui.QRhiSwapChain`.
