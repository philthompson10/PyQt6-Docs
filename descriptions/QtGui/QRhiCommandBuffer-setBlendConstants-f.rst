.. sip:method-description::
    :status: todo
    :pysig: 5237000fc3bc4f513a579caca380c129
    :realsig: (const QColor&)
    :digest: 3c223de23a1a9b183ed1f5096257a914

Records setting the active blend constants to *c*.

This can only be called when the bound pipeline has :sip:ref:`~PyQt6.QtGui.QRhiGraphicsPipeline.Flag.UsesBlendConstants` set.

**Note:** This function can only be called inside a render pass, meaning between a :sip:ref:`~PyQt6.QtGui.QRhiCommandBuffer.beginPass` and :sip:ref:`~PyQt6.QtGui.QRhiCommandBuffer.endPass` call.
