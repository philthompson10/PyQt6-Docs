.. sip:enum-member-description::
    :status: todo
    :value: 12
    :digest: 539c4b0759fbabb9057a2a485f001942

The number of bytes that can be exposed from a uniform buffer to the shaders at once. On OpenGL ES 2.0 and 3.0 implementations this may be as low as 3584 bytes (224 four component, 32 bits per component vectors). Elsewhere the value is typically 16384 (1024 vec4s) or 65536 (4096 vec4s).
