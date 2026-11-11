.. sip:enum-member-description::
    :status: todo
    :value: 27
    :digest: e4000443e32b84afd2c8a493e78bfa6d

Indicates that specifying a custom stride (row length) for raw image data in texture uploads is supported. When not supported (which can happen when the underlying API is OpenGL ES 2.0 without support for GL_UNPACK_ROW_LENGTH), QRhiTextureSubresourceUploadDescription::setDataStride() must not be used.
