.. sip:method-description::
    :status: todo
    :pysig: 0f51bf78fd261bd91cef73c5b53298c5
    :realsig: (int, int, const QRhiCommandBuffer::VertexInput*, QRhiBuffer*, quint32, QRhiCommandBuffer::IndexFormat)
    :digest: 359b049b923fac290929c08a11760d06

Records vertex input bindings.

The index buffer used by subsequent :sip:ref:`~PyQt6.QtGui.QRhiCommandBuffer.drawIndexed` commands is specified by *indexBuf*, *indexOffset*, and *indexFormat*. *indexBuf* can be set to null when indexed drawing is not needed.

Vertex buffer bindings are batched. *startBinding* specifies the first binding number. The recorded command then binds each buffer from *bindings* to the binding point ``startBinding + i`` where ``i`` is the index in *bindings*. Each element in *bindings* specifies a :sip:ref:`~PyQt6.QtGui.QRhiBuffer` and an offset.

**Note:** Some backends may limit the number of vertex buffer bindings. Avoid using a *bindingCount* larger than 8.

Superfluous vertex input and index changes in the same pass are ignored automatically with most backends and therefore applications do not need to overoptimize to avoid calls to this function.

**Note:** This function can only be called inside a render pass, meaning between a :sip:ref:`~PyQt6.QtGui.QRhiCommandBuffer.beginPass` and :sip:ref:`~PyQt6.QtGui.QRhiCommandBuffer.endPass` call.

As a simple example, take a vertex shader with two inputs:

::

    layout(location = 0) in vec4 position;
    layout(location = 1) in vec3 color;

and assume we have the data available in interleaved format, using only 2 floats for position (so 5 floats per vertex: x, y, r, g, b). A :sip:ref:`~PyQt6.QtGui.QRhiGraphicsPipeline` for this shader can then be created using the input layout:

::

    QRhiVertexInputLayout inputLayout;
    inputLayout.setBindings({
        { 5 * sizeof(float) }
    });
    inputLayout.setAttributes({
        { 0, 0, QRhiVertexInputAttribute::Float2, 0 },
        { 0, 1, QRhiVertexInputAttribute::Float3, 2 * sizeof(float) }
    });

Here there is one buffer binding (binding number 0), with two inputs referencing it. When recording the pass, once the pipeline is set, the vertex bindings can be specified simply like the following, assuming vbuf is the :sip:ref:`~PyQt6.QtGui.QRhiBuffer` with all the interleaved position+color data:

::

    const QRhiCommandBuffer::VertexInput vbufBinding(vbuf, 0);
    cb->setVertexInput(0, 1, &vbufBinding);
