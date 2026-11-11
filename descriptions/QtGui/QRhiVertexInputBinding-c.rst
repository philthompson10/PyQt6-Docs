.. sip:class-description::
    :status: todo
    :brief: Describes a vertex input binding
    :digest: 955ebe3be7a0042c0213ed603bd0feb7

Describes a vertex input binding.

Specifies the stride (in bytes, must be a multiple of 4), the classification and optionally the instance step rate.

As an example, assume a vertex shader with the following inputs:

::

    layout(location = 0) in vec4 position;
    layout(location = 1) in vec2 texcoord;

Now let's assume also that 3 component vertex positions ``(x, y, z)`` and 2 component texture coordinates ``(u, v)`` are provided in a non-interleaved format in a buffer (or separate buffers even). Defining two bindings could then be done like this:

::

    QRhiVertexInputLayout inputLayout;
    inputLayout.setBindings({
        { 3 * sizeof(float) },
        { 2 * sizeof(float) }
    });

Only the stride is interesting here since instancing is not used. The binding number is given by the index of the :sip:ref:`~PyQt6.QtGui.QRhiVertexInputBinding` element in the bindings vector of the :sip:ref:`~PyQt6.QtGui.QRhiVertexInputLayout`.

Once a graphics pipeline with this vertex input layout is bound, the vertex inputs could be set up like the following for drawing a cube with 36 vertices, assuming we have a single buffer with first the positions and then the texture coordinates:

::

    const QRhiCommandBuffer::VertexInput vbufBindings[] = {
        { cubeBuf, 0 },
        { cubeBuf, 36 * 3 * sizeof(float) }
    };
    cb->setVertexInput(0, 2, vbufBindings);

Note how the index defined by ``startBinding + i``, where ``i`` is the index in the second argument of :sip:ref:`~PyQt6.QtGui.QRhiCommandBuffer.setVertexInput`, matches the index of the corresponding entry in the ``bindings`` vector of the :sip:ref:`~PyQt6.QtGui.QRhiVertexInputLayout`.

**Note:** the stride must always be a multiple of 4.

**Note:** This is a RHI API with limited compatibility guarantees, see :sip:ref:`~PyQt6.QtGui.QRhi` for details.

.. seealso:: :sip:ref:`~PyQt6.QtGui.QRhiCommandBuffer.setVertexInput`.
