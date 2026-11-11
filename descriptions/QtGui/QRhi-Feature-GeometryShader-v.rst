.. sip:enum-member-description::
    :status: todo
    :value: 33
    :digest: 2c94c346ffc435726be8d9e3d59da0e3

Indicates that the geometry shader stage is supported. When supported, a geometry shader can be specified in the :sip:ref:`~PyQt6.QtGui.QRhiShaderStage` list. Geometry Shaders are considered an experimental feature in :sip:ref:`~PyQt6.QtGui.QRhi` and can only be expected to be supported with Vulkan, Direct 3D 11 and 12, OpenGL (3.2+) and OpenGL ES (3.2+), assuming the implementation reports it as supported at run time. Starting with Qt 6.11 geometry shaders are automatically translated to HLSL, and therefore no injection of handwritten HLSL geometry shaders is necessary anymore (but note that gl_in and expressions such as gl_in[0].gl_Position are not supported; rather, pass the position as an output variable from the vertex shader). Geometry shaders are not supported with Metal.
