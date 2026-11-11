.. sip:method-description::
    :status: todo
    :pysig: 9aedf15684ca1c7d195229b10efe2c66
    :realsig: (QRhiSwapChain*, QRhi::BeginFrameFlags)
    :digest: fe6e83ae0fa2313db5ccda8f8c1aa51f

Starts a new frame targeting the next available buffer of *swapChain*.

A frame consists of resource updates and one or more render and compute passes.

*flags* can indicate certain special cases.

The high level pattern of rendering into a :sip:ref:`~PyQt6.QtGui.QWindow` using a swapchain:

* Create a swapchain.

* Call QRhiSwapChain::createOrResize() whenever the surface size is different than before.

* Call QRhiSwapChain::destroy() on :sip:ref:`~PyQt6.QtGui.QPlatformSurfaceEvent.SurfaceEventType.SurfaceAboutToBeDestroyed`.

* Then on every frame:

  ::

      beginFrame(sc);
      updates = nextResourceUpdateBatch();
      updates->...
      QRhiCommandBuffer *cb = sc->currentFrameCommandBuffer();
      cb->beginPass(sc->currentFrameRenderTarget(), colorClear, dsClear, updates);
      ...
      cb->endPass();
      ... // more passes as necessary
      endFrame(sc);

Returns :sip:ref:`~PyQt6.QtGui.QRhi.FrameOpResult.FrameOpSuccess` on success, or another :sip:ref:`~PyQt6.QtGui.QRhi.FrameOpResult` value on failure. Some of these should be treated as soft, "try again later" type of errors: When :sip:ref:`~PyQt6.QtGui.QRhi.FrameOpResult.FrameOpSwapChainOutOfDate` is returned, the swapchain is to be resized or updated by calling QRhiSwapChain::createOrResize(). The application should then attempt to generate a new frame. :sip:ref:`~PyQt6.QtGui.QRhi.FrameOpResult.FrameOpDeviceLost` means the graphics device is lost but this may also be recoverable by releasing all resources, including the :sip:ref:`~PyQt6.QtGui.QRhi` itself, and then recreating all resources. See :sip:ref:`~PyQt6.QtGui.QRhi.isDeviceLost` for further discussion.

.. seealso:: :sip:ref:`~PyQt6.QtGui.QRhi.endFrame`, :sip:ref:`~PyQt6.QtGui.QRhi.beginOffscreenFrame`, :sip:ref:`~PyQt6.QtGui.QRhi.isDeviceLost`.
