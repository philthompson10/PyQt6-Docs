.. sip:method-description::
    :status: todo
    :pysig: 55a9b1b70dfd37ff3574d6a71d16727e
    :realsig: (QRhiComputePipeline*)
    :digest: 3b6380ba1a94eb4b2fe8a23079035f38

Records setting a new compute pipeline *ps*.

**Note:** This function must be called before recording :sip:ref:`~PyQt6.QtGui.QRhiCommandBuffer.setShaderResources` or :sip:ref:`~PyQt6.QtGui.QRhiCommandBuffer.dispatch` commands on the command buffer.

**Note:** :sip:ref:`~PyQt6.QtGui.QRhi` will optimize out unnecessary invocations within a pass, so therefore overoptimizing to avoid calls to this function is not necessary on the applications' side.

**Note:** This function can only be called inside a compute pass, meaning between a :sip:ref:`~PyQt6.QtGui.QRhiCommandBuffer.beginComputePass` and :sip:ref:`~PyQt6.QtGui.QRhiCommandBuffer.endComputePass` call.
