.. sip:enum-member-description::
    :status: todo
    :value: 38
    :digest: 327da6cb056fa7362e00e7dcfbc806b1

Indicates that specifying input attributes with half precision (16bit) floating point types for a shader pipeline is supported. When not supported, QRhiGraphicsPipeline::create() will succeed but show a warning message and the values of the target attributes will be broken. In practice this feature will be unsupported in some OpenGL ES 2.0 and OpenGL 2.x implementations. Note that while Direct3D 11/12 does support half precision input attributes, it does not support the half3 type. The D3D backends pass half3 attributes as half4. To ensure cross platform compatibility, half3 inputs should be padded to 8 bytes.
