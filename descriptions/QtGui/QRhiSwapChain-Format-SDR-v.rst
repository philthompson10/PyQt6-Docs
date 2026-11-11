.. sip:enum-member-description::
    :status: todo
    :value: 0
    :digest: 84e80912a74e38f6c9b4293beda86649

8-bit RGBA or BGRA, depending on the backend and platform. With OpenGL ES in particular, it could happen that the platform provides less than 8 bits (e.g. due to EGL and the :sip:ref:`~PyQt6.QtGui.QSurfaceFormat` choosing a 565 or 444 format - this is outside the control of :sip:ref:`~PyQt6.QtGui.QRhi`). Standard dynamic range. May be combined with setting the :sip:ref:`~PyQt6.QtGui.QRhiSwapChain.Flag.sRGB` flag.
