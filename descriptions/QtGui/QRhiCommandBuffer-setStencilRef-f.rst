.. sip:method-description::
    :status: todo
    :pysig: fa7153f7ed1cb6c0fcf2ffb2fac21748
    :realsig: (quint32)
    :digest: 8be99dff23ccdecaf6c8d25e84fce884

Records setting the active stencil reference value to *refValue*.

This can only be called when the bound pipeline has :sip:ref:`~PyQt6.QtGui.QRhiGraphicsPipeline.Flag.UsesStencilRef` set.

**Note:** This function can only be called inside a render pass, meaning between a :sip:ref:`~PyQt6.QtGui.QRhiCommandBuffer.beginPass` and :sip:ref:`~PyQt6.QtGui.QRhiCommandBuffer.endPass` call.
