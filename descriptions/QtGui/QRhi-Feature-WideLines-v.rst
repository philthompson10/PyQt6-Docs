.. sip:enum-member-description::
    :status: todo
    :value: 14
    :digest: 5811c936c82216bc70b2bf98623f2c8d

Indicates that lines with a width other than 1 are supported. When reported as not supported, the line width set on the graphics pipeline state is ignored. This can always be false with some backends (D3D11, D3D12, Metal). With Vulkan, the value depends on the implementation. With OpenGL, wide lines are not supported in core profile contexts.
