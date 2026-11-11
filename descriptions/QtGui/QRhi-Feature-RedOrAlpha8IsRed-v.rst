.. sip:enum-member-description::
    :status: todo
    :value: 11
    :digest: 76d192517c874eb002a964cefd793e69

Indicates that the :sip:ref:`~PyQt6.QtGui.QRhiTexture.Format.RED_OR_ALPHA8` format maps to a one component 8-bit ``red`` format. This is the case for all backends except OpenGL when using either OpenGL ES or a non-core profile context. There ``GL_ALPHA``, a one component 8-bit ``alpha`` format, is used instead. Using the special texture format allows having a single code path for creating textures, leaving it up to the backend to decide the actual format, while the feature flag can be used to pick the appropriate shader variant for sampling the texture.
