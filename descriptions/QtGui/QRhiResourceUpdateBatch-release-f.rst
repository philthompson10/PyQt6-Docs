.. sip:method-description::
    :status: todo
    :pysig: d41d8cd98f00b204e9800998ecf8427e
    :realsig: ()
    :digest: 1342370125eafaa44bdee6832ea16daf

Returns the batch to the pool. This should only be used when the batch is not passed to one of :sip:ref:`~PyQt6.QtGui.QRhiCommandBuffer.beginPass`, :sip:ref:`~PyQt6.QtGui.QRhiCommandBuffer.endPass`, or :sip:ref:`~PyQt6.QtGui.QRhiCommandBuffer.resourceUpdate` because these implicitly call destroy().

**Note:** :sip:ref:`~PyQt6.QtGui.QRhiResourceUpdateBatch` instances must never by ``deleted`` by applications.
