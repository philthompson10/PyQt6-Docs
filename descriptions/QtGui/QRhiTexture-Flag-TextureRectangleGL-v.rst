.. sip:enum-member-description::
    :status: todo
    :value: 1 << 11
    :digest: 9e3d4a455ee97b60f5e1343f12bcc0c0

The texture should use the GL_TEXTURE_RECTANGLE target with OpenGL. This flag is ignored with other graphics APIs. Just like ExternalOES, this flag is useful when working with platform APIs where native OpenGL texture objects received from the platform are wrapped in a :sip:ref:`~PyQt6.QtGui.QRhiTexture`, and the platform can only provide textures for a non-2D texture target.
