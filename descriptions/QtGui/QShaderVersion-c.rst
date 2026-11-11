.. sip:class-description::
    :status: todo
    :brief: Specifies the shading language version
    :digest: abe39c605c38226d126dd4e71d73ae40

Specifies the shading language version.

While languages like SPIR-V or the Metal Shading Language use traditional version numbers, shaders for other APIs can use slightly different versioning schemes. All those are mapped to a single version number in here, however. For HLSL, the version refers to the Shader Model version, like 5.0, 5.1, or 6.0. For GLSL an additional flag is needed to choose between GLSL and GLSL/ES.

Below is a list with the most common examples of shader versions for different graphics APIs:

* Vulkan (SPIR-V): 100

* OpenGL: 120, 330, 440, etc.

* OpenGL ES: 100 with :sip:ref:`~PyQt6.QtGui.QShaderVersion.Flag.GlslEs`, 300 with :sip:ref:`~PyQt6.QtGui.QShaderVersion.Flag.GlslEs`, etc.

* Direct3D: 50, 51, 60

* Metal: 12, 20

A default constructed :sip:ref:`~PyQt6.QtGui.QShaderVersion` contains a version of 100 and no flags set.

**Note:** This is a RHI API with limited compatibility guarantees, see :sip:ref:`~PyQt6.QtGui.QShader` for details.
