.. sip:method-description::
    :status: todo
    :pysig: 3bc5fb742156fbbc25d5fb97ade69b88
    :realsig: (QRhiBuffer*, quint32, quint32, QRhiReadbackResult*)
    :digest: 1948239a842de2cb37ef837cb5999d65

Enqueues reading back a region of the :sip:ref:`~PyQt6.QtGui.QRhiBuffer` *buf*. The size of the region is specified by *size* in bytes, *offset* is the offset in bytes to start reading from.

A readback is asynchronous. *result* contains a callback that is invoked when the operation has completed. The data is provided in QRhiReadbackResult::data. Upon successful completion that :sip:ref:`~PyQt6.QtCore.QByteArray` will have a size equal to *size*. On failure the :sip:ref:`~PyQt6.QtCore.QByteArray` will be empty.

**Note:** Reading buffers with a usage different than :sip:ref:`~PyQt6.QtGui.QRhiBuffer.UsageFlag.UniformBuffer` is supported only when the :sip:ref:`~PyQt6.QtGui.QRhi.Feature.ReadBackNonUniformBuffer` feature is reported as supported.

**Note:** The asynchronous readback is guaranteed to have completed when one of the following conditions is met: :sip:ref:`~PyQt6.QtGui.QRhi.finish` has been called; or, at least ``N`` frames have been :sip:ref:`~PyQt6.QtGui.QRhi.endFrame`, including the frame that issued the readback operation, and the :sip:ref:`~PyQt6.QtGui.QRhi.beginFrame` has been started, where ``N`` is the :sip:ref:`~PyQt6.QtGui.QRhi.resourceLimit` returned for :sip:ref:`~PyQt6.QtGui.QRhi.ResourceLimit.MaxAsyncReadbackFrames`.

.. seealso:: :sip:ref:`~PyQt6.QtGui.QRhiResourceUpdateBatch.readBackTexture`, :sip:ref:`~PyQt6.QtGui.QRhi.isFeatureSupported`, :sip:ref:`~PyQt6.QtGui.QRhi.resourceLimit`.
