.. sip:method-description::
    :status: todo
    :pysig: 1151083e4a7412852a3e0982c7ce5327
    :realsig: (QRhiSwapChain::StereoTargetBuffer)
    :digest: b187776f04e06316b6fbc47498135fc6

Returns a render target that can be used with beginPass() in order to render to the swapchain's left or right backbuffer. This overload should be used only with stereoscopic rendering, that is, when the associated :sip:ref:`~PyQt6.QtGui.QWindow` is backed by two color buffers, one for each eye, instead of just one.

When stereoscopic rendering is not supported, the return value will be the default target. It is supported by all hardware backends except for Metal, in combination with :sip:ref:`~PyQt6.QtGui.QSurfaceFormat.FormatOption.StereoBuffers`, assuming it is supported by the graphics and display driver stack at run time. Metal and Null backends are going to return the default render target from this overload.

**Note:** the value must not be cached and reused between frames
