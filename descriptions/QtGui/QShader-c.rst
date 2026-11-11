.. sip:class-description::
    :status: todo
    :brief: Contains multiple versions of a shader translated to multiple shading languages, together with reflection metadata
    :digest: e2a021be45049196f5581bac854b8273

Contains multiple versions of a shader translated to multiple shading languages, together with reflection metadata.

:sip:ref:`~PyQt6.QtGui.QShader` is the entry point to shader code in the graphics API agnostic Qt world. Instead of using GLSL shader sources, as was the custom with Qt 5.x, new graphics systems with backends for multiple graphics APIs, such as, Vulkan, Metal, Direct3D, and OpenGL, take :sip:ref:`~PyQt6.QtGui.QShader` as their input whenever a shader needs to be specified.

**Warning:** The :sip:ref:`~PyQt6.QtGui.QRhi` family of classes in the Qt Gui module, including :sip:ref:`~PyQt6.QtGui.QShader` and :sip:ref:`~PyQt6.QtGui.QShaderDescription`, offer limited compatibility guarantees. There are no source or binary compatibility guarantees for these classes, meaning the API is only guaranteed to work with the Qt version the application was developed against. Source incompatible changes are however aimed to be kept at a minimum and will only be made in minor releases (6.7, 6.8, and so on). To use these classes in an application, link to ``Qt::GuiPrivate`` (if using CMake), and include the headers with the ``rhi`` prefix, for example ``#include <rhi/qshader.h>``.

A :sip:ref:`~PyQt6.QtGui.QShader` instance is empty and thus invalid by default. To get a useful instance, the two typical methods are:

* Generate the contents offline, during build time or earlier, using the ``qsb`` command line tool. The result is a binary file that is shipped with the application, read via :sip:ref:`~PyQt6.QtCore.QIODevice.readAll`, and then deserialized via :sip:ref:`~PyQt6.QtGui.QShader.fromSerialized`. For more information, see QShaderBaker.

* Generate at run time via QShaderBaker. This is an expensive operation, but allows applications to use user-provided or dynamically generated shader source strings.

When used together with the Qt Rendering Hardware Interface and its classes, like :sip:ref:`~PyQt6.QtGui.QRhiGraphicsPipeline`, no further action is needed from the application's side as these classes are prepared to consume a :sip:ref:`~PyQt6.QtGui.QShader` whenever a shader needs to be specified for a given stage of the graphics pipeline.

Alternatively, applications can access

* the source or byte code for any of the shading language versions that are included in the :sip:ref:`~PyQt6.QtGui.QShader`,

* the name of the entry point for the shader,

* the reflection metadata containing a description of the shader's inputs, outputs and resources like uniform blocks. This is essential when an application or framework needs to discover the inputs of a shader at runtime due to not having advance knowledge of the vertex attributes or the layout of the uniform buffers used by the shader.

:sip:ref:`~PyQt6.QtGui.QShader` makes no assumption about the shading language that was used as the source for generating the various versions and variants that are included in it.

:sip:ref:`~PyQt6.QtGui.QShader` uses implicit sharing similarly to many core Qt types, and so can be returned or passed by value. Detach happens implicitly when calling a setter.

For reference, a typical, portable :sip:ref:`~PyQt6.QtGui.QRhi` expects that a :sip:ref:`~PyQt6.QtGui.QShader` suitable for all its backends contains at least the following. (this excludes support for core profile OpenGL contexts, add GLSL 150 or newer for that)

* SPIR-V 1.0 bytecode suitable for Vulkan 1.0 or newer

* GLSL/ES 100 source code suitable for OpenGL ES 2.0 or newer

* GLSL 120 source code suitable for OpenGL 2.1 or newer

* HLSL Shader Model 5.0 source code or the corresponding DXBC bytecode suitable for Direct3D 11/12

* Metal Shading Language 1.2 source code or the corresponding bytecode suitable for Metal 1.2 or newer

.. seealso:: QShaderBaker.
