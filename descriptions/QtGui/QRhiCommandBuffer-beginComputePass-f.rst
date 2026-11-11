.. sip:method-description::
    :status: todo
    :pysig: 766d24702559dea6aa148a74d489e2a9
    :realsig: (QRhiResourceUpdateBatch*, QRhiCommandBuffer::BeginPassFlags)
    :digest: 01386dd619904b0647ac04c224e85c53

Records starting a new compute pass.

*resourceUpdates*, when not null, specifies a resource update batch that is to be committed and then released.

**Note:** Do not assume that any state or resource bindings persist between passes.

**Note:** A compute pass can record :sip:ref:`~PyQt6.QtGui.QRhiCommandBuffer.setComputePipeline`, :sip:ref:`~PyQt6.QtGui.QRhiCommandBuffer.setShaderResources`, and :sip:ref:`~PyQt6.QtGui.QRhiCommandBuffer.dispatch` calls, not graphics ones. General functionality, such as, debug markers and :sip:ref:`~PyQt6.QtGui.QRhiCommandBuffer.beginExternal` is available both in render and compute passes.

**Note:** Compute is only available when the :sip:ref:`~PyQt6.QtGui.QRhi.Feature.Compute` feature is reported as supported.

*flags* is not currently used.
