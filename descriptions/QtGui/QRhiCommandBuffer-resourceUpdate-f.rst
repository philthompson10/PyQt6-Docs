.. sip:method-description::
    :status: todo
    :pysig: 7e42f4080e1ed0b2e41b452b4fdbaba3
    :realsig: (QRhiResourceUpdateBatch*)
    :digest: 9b636f82b7d86f5cb6e68c5b2811a182

Sometimes committing resource updates is necessary or just more convenient without starting a render pass. Calling this function with *resourceUpdates* is an alternative to passing *resourceUpdates* to a :sip:ref:`~PyQt6.QtGui.QRhiCommandBuffer.beginPass` call (or :sip:ref:`~PyQt6.QtGui.QRhiCommandBuffer.endPass`, which would be typical in case of readbacks).

**Note:** Cannot be called inside a pass.
