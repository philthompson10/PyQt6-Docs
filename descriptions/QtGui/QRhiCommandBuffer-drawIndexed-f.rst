.. sip:method-description::
    :status: todo
    :pysig: 163c40cc404c3571dc4f69554a001652
    :realsig: (quint32, quint32, quint32, qint32, quint32)
    :digest: c47d77c9b9359bff25f3b103d3f619f1

Records an indexed draw.

The number of vertices is specified in *indexCount*. *firstIndex* is the base index. The effective offset in the index buffer is given by ``indexOffset + firstIndex \* n`` where ``n`` is 2 or 4 depending on the index element type. ``indexOffset`` is specified in :sip:ref:`~PyQt6.QtGui.QRhiCommandBuffer.setVertexInput`.

**Note:** The effective offset in the index buffer must be 4 byte aligned with some backends (for example, Metal). With these backends the :sip:ref:`~PyQt6.QtGui.QRhi.Feature.NonFourAlignedEffectiveIndexBufferOffset` feature will be reported as not-supported.

*vertexOffset* (also called ``base vertex``) is a signed value that is added to the element index before indexing into the vertex buffer. Support for this is not always available, and the value is ignored when the feature :sip:ref:`~PyQt6.QtGui.QRhi.Feature.BaseVertex` is reported as unsupported.

For instanced drawing set *instanceCount* to a value other than 1. When drawing multiple instances, the first instance ID is specified by *firstInstance*.

**Note:** *firstInstance* may not be supported, and is ignored when the :sip:ref:`~PyQt6.QtGui.QRhi.Feature.BaseInstance` feature is reported as not supported. The first instance ID is always 0 in that case. :sip:ref:`~PyQt6.QtGui.QRhi.Feature.BaseInstance` is never supported with OpenGL at the moment, mainly due to OpenGL ES limitations, and therefore portable applications should not be designed to rely on this argument.

**Note:** Shaders that need to access the index of the current vertex or instance must use ``gl_VertexIndex`` and ``gl_InstanceIndex``, i.e., the Vulkan-compatible built-in variables, instead of ``gl_VertexID`` and ``gl_InstanceID``.

**Note:** When *firstInstance* is non-zero, ``gl_InstanceIndex`` will not include the base value with some of the underlying 3D APIs. This is indicated by the :sip:ref:`~PyQt6.QtGui.QRhi.Feature.InstanceIndexIncludesBaseInstance` feature. If relying on a base instance value cannot be avoided, applications are advised to pass in the value as a uniform conditionally based on what that feature reports, and add it to ``gl_InstanceIndex`` in the shader.

**Note:** This function can only be called inside a render pass, meaning between a :sip:ref:`~PyQt6.QtGui.QRhiCommandBuffer.beginPass` and :sip:ref:`~PyQt6.QtGui.QRhiCommandBuffer.endPass` call.
