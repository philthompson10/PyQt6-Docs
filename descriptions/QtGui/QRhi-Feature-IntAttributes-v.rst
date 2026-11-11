.. sip:enum-member-description::
    :status: todo
    :value: 23
    :digest: 7b00203387b5bdb37aa951ce9c03f23f

Indicates that specifying input attributes with signed and unsigned integer types for a shader pipeline is supported. When not supported, QRhiGraphicsPipeline::create() will succeed but show a warning message and the values of the target attributes will be broken. In practice this feature will be unsupported with OpenGL ES 2.0 and OpenGL 2.x.
