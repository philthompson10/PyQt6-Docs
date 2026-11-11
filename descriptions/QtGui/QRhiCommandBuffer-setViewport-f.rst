.. sip:method-description::
    :status: todo
    :pysig: 74073e65dc8d41b2ddefa54586b26eb4
    :realsig: (const QRhiViewport&)
    :digest: 1cd5364659497e67e0d2aab1bfef44d8

Records setting the active viewport rectangle specified in *viewport*.

With backends where the underlying graphics API has scissoring always enabled, this function also sets the scissor to match the viewport whenever the active :sip:ref:`~PyQt6.QtGui.QRhiGraphicsPipeline` does not have :sip:ref:`~PyQt6.QtGui.QRhiGraphicsPipeline.Flag.UsesScissor` set.

**Note:** :sip:ref:`~PyQt6.QtGui.QRhi` assumes OpenGL-style viewport coordinates, meaning x and y are bottom-left.

**Note:** This function can only be called inside a render pass, meaning between a :sip:ref:`~PyQt6.QtGui.QRhiCommandBuffer.beginPass` and :sip:ref:`~PyQt6.QtGui.QRhiCommandBuffer.endPass` call.
