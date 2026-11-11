.. sip:class-description::
    :status: todo
    :brief: Describes the layout of vertex inputs consumed by a vertex shader
    :digest: c91d93af7e22f37c9e8806ed22a6fea7

Describes the layout of vertex inputs consumed by a vertex shader.

The vertex input layout is defined by the collections of :sip:ref:`~PyQt6.QtGui.QRhiVertexInputBinding` and :sip:ref:`~PyQt6.QtGui.QRhiVertexInputAttribute`.

As an example, let's assume that we have a single buffer with 3 component vertex positions and 2 component UV coordinates interleaved (``x``, ``y``, ``z``, ``u``, ``v``), that the position and UV are expected at input locations 0 and 1 by the vertex shader, and that the vertex buffer will be bound at binding point 0 using :sip:ref:`~PyQt6.QtGui.QRhiCommandBuffer.setVertexInput` later on:

::

    QRhiVertexInputLayout inputLayout;
    inputLayout.setBindings({
        { 5 * sizeof(float) }
    });
    inputLayout.setAttributes({
        { 0, 0, QRhiVertexInputAttribute::Float3, 0 },
        { 0, 1, QRhiVertexInputAttribute::Float2, 3 * sizeof(float) }
    });

**Note:** This is a RHI API with limited compatibility guarantees, see :sip:ref:`~PyQt6.QtGui.QRhi` for details.
