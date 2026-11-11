.. sip:enum-member-description::
    :status: todo
    :value: 1 << 2
    :digest: 6681c3dcaf481ddf994c7676b24451c4

Requests to pick an sRGB format for the swapchain's color buffers and/or render target views, where applicable. Note that this implies that sRGB framebuffer update and blending will get enabled for all content targeting this swapchain, and opting out is not possible. For OpenGL, set sRGBColorSpace on the :sip:ref:`~PyQt6.QtGui.QSurfaceFormat` of the :sip:ref:`~PyQt6.QtGui.QWindow` in addition. Applicable only when the swapchain format is set to :sip:ref:`~PyQt6.QtGui.QRhiSwapChain.Format.SDR`.
