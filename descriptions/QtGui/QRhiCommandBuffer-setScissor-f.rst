.. sip:method-description::
    :status: todo
    :pysig: 9113b453af84171cdd76a3c5c30deb64
    :realsig: (const QRhiScissor&)
    :digest: d4ffa400fafb67cfba35fee41ec7bb71

Records setting the active scissor rectangle specified in *scissor*.

This can only be called when the bound pipeline has :sip:ref:`~PyQt6.QtGui.QRhiGraphicsPipeline.Flag.UsesScissor` set. When the flag is set on the active pipeline, this function must be called because scissor testing will get enabled and so a scissor rectangle must be provided.

**Note:** :sip:ref:`~PyQt6.QtGui.QRhi` assumes OpenGL-style viewport coordinates, meaning x and y are bottom-left.

**Note:** This function can only be called inside a render pass, meaning between a :sip:ref:`~PyQt6.QtGui.QRhiCommandBuffer.beginPass` and :sip:ref:`~PyQt6.QtGui.QRhiCommandBuffer.endPass` call.
