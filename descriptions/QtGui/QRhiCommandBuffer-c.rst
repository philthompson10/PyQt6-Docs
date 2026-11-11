.. sip:class-description::
    :status: todo
    :brief: Command buffer resource
    :digest: f90f8bc68b8b5e9f55295c2e22abcc23

Command buffer resource.

Not creatable by applications at the moment. The only ways to obtain a valid :sip:ref:`~PyQt6.QtGui.QRhiCommandBuffer` are to get it from the targeted swapchain via QRhiSwapChain::currentFrameCommandBuffer(), or, in case of rendering completely offscreen, initializing one via :sip:ref:`~PyQt6.QtGui.QRhi.beginOffscreenFrame`.

**Note:** This is a RHI API with limited compatibility guarantees, see :sip:ref:`~PyQt6.QtGui.QRhi` for details.
