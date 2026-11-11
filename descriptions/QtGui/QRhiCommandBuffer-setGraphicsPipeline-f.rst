.. sip:method-description::
    :status: todo
    :pysig: 054a01456df157375549deaaa5c17cbc
    :realsig: (QRhiGraphicsPipeline*)
    :digest: 99f02aee89784324e91b73ea96644ab2

Records setting a new graphics pipeline *ps*.

**Note:** This function must be called before recording other ``set`` or ``draw`` commands on the command buffer.

**Note:** :sip:ref:`~PyQt6.QtGui.QRhi` will optimize out unnecessary invocations within a pass, so therefore overoptimizing to avoid calls to this function is not necessary on the applications' side.

**Note:** This function can only be called inside a render pass, meaning between a :sip:ref:`~PyQt6.QtGui.QRhiCommandBuffer.beginPass` and :sip:ref:`~PyQt6.QtGui.QRhiCommandBuffer.endPass` call.

**Note:** The new graphics pipeline *ps* must be a valid pointer.

Setting a graphics pipeline that does not have the :sip:ref:`~PyQt6.QtGui.QRhiGraphicsPipeline.Flag.UsesScissor` flag will either disable scissoring, with graphics APIs where that is applicable, or set the scissor rectangle to match the viewport that was last set (with graphics APIs where scissoring is effectively always active), in order to ensure a uniform behavior across :sip:ref:`~PyQt6.QtGui.QRhi` backends.
