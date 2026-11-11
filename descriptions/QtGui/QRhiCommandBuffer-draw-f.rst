.. sip:method-description::
    :status: todo
    :pysig: 98ccc28e9838b116227b00b85f61e978
    :realsig: (quint32, quint32, quint32, quint32)
    :digest: 8d9c3e8f67734ac7d4c8b550df381124

Records a non-indexed draw.

The number of vertices is specified in *vertexCount*. For instanced drawing set *instanceCount* to a value other than 1. *firstVertex* is the index of the first vertex to draw. When drawing multiple instances, the first instance ID is specified by *firstInstance*.

**Note:** *firstInstance* may not be supported, and is ignored when the :sip:ref:`~PyQt6.QtGui.QRhi.Feature.BaseInstance` feature is reported as not supported. The first instance ID is always 0 in that case. :sip:ref:`~PyQt6.QtGui.QRhi.Feature.BaseInstance` is never supported with OpenGL at the moment, mainly due to OpenGL ES limitations, and therefore portable applications should not be designed to rely on this argument.

**Note:** Shaders that need to access the index of the current vertex or instance must use ``gl_VertexIndex`` and ``gl_InstanceIndex``, i.e., the Vulkan-compatible built-in variables, instead of ``gl_VertexID`` and ``gl_InstanceID``.

**Note:** When *firstInstance* is non-zero, ``gl_InstanceIndex`` will not include the base value with some of the underlying 3D APIs. This is indicated by the :sip:ref:`~PyQt6.QtGui.QRhi.Feature.InstanceIndexIncludesBaseInstance` feature. If relying on a base instance value cannot be avoided, applications are advised to pass in the value as a uniform conditionally based on what that feature reports, and add it to ``gl_InstanceIndex`` in the shader.

**Note:** This function can only be called inside a render pass, meaning between a :sip:ref:`~PyQt6.QtGui.QRhiCommandBuffer.beginPass` and :sip:ref:`~PyQt6.QtGui.QRhiCommandBuffer.endPass` call.
