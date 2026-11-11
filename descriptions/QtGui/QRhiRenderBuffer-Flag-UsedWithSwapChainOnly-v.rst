.. sip:enum-member-description::
    :status: todo
    :value: 1 << 0
    :digest: 95ce81d8dfe21da3cdd84de15a3ca281

For :sip:ref:`~PyQt6.QtGui.QRhiRenderBuffer.Type.DepthStencil` renderbuffers this indicates that the renderbuffer is only used in combination with a :sip:ref:`~PyQt6.QtGui.QRhiSwapChain`, and never in any other way. This provides automatic sizing and resource rebuilding, so calling setPixelSize() or create() is not needed whenever this flag is set. This flag value may also trigger backend-specific behavior, for example with OpenGL, where a separate windowing system interface API is in use (EGL, GLX, etc.), the flag is especially important as it avoids creating any actual renderbuffer resource as there is already a windowing system provided depth/stencil buffer as requested by :sip:ref:`~PyQt6.QtGui.QSurfaceFormat`.
