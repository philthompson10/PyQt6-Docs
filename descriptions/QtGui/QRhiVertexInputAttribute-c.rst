.. sip:class-description::
    :status: todo
    :brief: Describes a single vertex input element
    :digest: 08d4255f97b97453f91d1e1c6f6605df

Describes a single vertex input element.

The members specify the binding number, location, format, and offset for a single vertex input element.

**Note:** For HLSL it is assumed that the vertex shader translated from SPIR-V uses ``TEXCOORD<location>`` as the semantic for each input. Hence no separate semantic name and index.

As an example, assume a vertex shader with the following inputs:

::

    layout(location = 0) in vec4 position;
    layout(location = 1) in vec2 texcoord;

Now let's assume that we have 3 component vertex positions ``(x, y, z)`` and 2 component texture coordinates ``(u, v)`` are provided in a non-interleaved format in a buffer (or separate buffers even). Once two bindings are defined, the attributes could be specified as:

::

    QRhiVertexInputLayout inputLayout;
    inputLayout.setBindings({
        { 3 * sizeof(float) },
        { 2 * sizeof(float) }
    });
    inputLayout.setAttributes({
        { 0, 0, QRhiVertexInputAttribute::Float3, 0 },
        { 1, 1, QRhiVertexInputAttribute::Float2, 0 }
    });

Once a graphics pipeline with this vertex input layout is bound, the vertex inputs could be set up like the following for drawing a cube with 36 vertices, assuming we have a single buffer with first the positions and then the texture coordinates:

::

    const QRhiCommandBuffer::VertexInput vbufBindings[] = {
        { cubeBuf, 0 },
        { cubeBuf, 36 * 3 * sizeof(float) }
    };
    cb->setVertexInput(0, 2, vbufBindings);

When working with interleaved data, there will typically be just one binding, with multiple attributes referring to that same buffer binding point:

::

    QRhiVertexInputLayout inputLayout;
    inputLayout.setBindings({
        { 5 * sizeof(float) }
    });
    inputLayout.setAttributes({
        { 0, 0, QRhiVertexInputAttribute::Float3, 0 },
        { 0, 1, QRhiVertexInputAttribute::Float2, 3 * sizeof(float) }
    });

and then:

::

    const QRhiCommandBuffer::VertexInput vbufBinding(interleavedCubeBuf, 0);
    cb->setVertexInput(0, 1, &vbufBinding);

**Note:** This is a RHI API with limited compatibility guarantees, see :sip:ref:`~PyQt6.QtGui.QRhi` for details.

.. seealso:: :sip:ref:`~PyQt6.QtGui.QRhiCommandBuffer.setVertexInput`.
