.. sip:method-description::
    :status: todo
    :pysig: a81d652f6b971c9d7e252e558e2dead2
    :realsig: (QRhiBuffer*, quint32, quint32, quint32)
    :digest: 75c8a0049e1d0a651ff586f8b7d909dc

Records a non-indexed, indirect draw.

The draw parameters are provided by the buffer specified in *indirectBuffer*, which must contain an array of elements of type :sip:ref:`~PyQt6.QtGui.QRhiIndirectDrawCommand`. The parameters in :sip:ref:`~PyQt6.QtGui.QRhiIndirectDrawCommand` have the same meaning as in :sip:ref:`~PyQt6.QtGui.QRhiCommandBuffer.draw`.

The offset, in bytes, from which the parameters are read in the buffer is specified by *indirectBufferOffset*.

*drawCount* specifies the number of such draw commands to issue.

*stride* indicates the byte size of each individual draw command structure in the buffer. This allows interleaving custom data between commands if needed. The value must be a multiple of 4 and greater than or equal to sizeof(\ :sip:ref:`~PyQt6.QtGui.QRhiIndirectDrawCommand`).

**Note:** A *drawCount* value greater than 1 is only natively supported if the :sip:ref:`~PyQt6.QtGui.QRhi.Feature.DrawIndirectMulti` feature is reported as supported and stride is the default. Otherwise, this function emulates multi-draw by recording multiple draw calls, offering no performance benefit over repeated :sip:ref:`~PyQt6.QtGui.QRhiCommandBuffer.draw` calls.

**Note:** This function can only be called inside a render pass, meaning between a :sip:ref:`~PyQt6.QtGui.QRhiCommandBuffer.beginPass` and :sip:ref:`~PyQt6.QtGui.QRhiCommandBuffer.endPass` call.
