.. sip:enum-member-description::
    :status: todo
    :value: 15
    :digest: a5efebf387f2c20f466028029cdb893b

Indicates that the size of rasterized points set via ``gl_PointSize`` in the vertex shader is taken into account. When reported as not supported, drawing points with a size other than 1 is not supported. Setting ``gl_PointSize`` in the shader is still valid then, but is ignored. (for example, when generating HLSL, the assignment is silently dropped from the generated code) Note that some APIs (Metal, Vulkan) require the point size to be set in the shader explicitly whenever drawing points, even when the size is 1, as they do not automatically default to 1.
