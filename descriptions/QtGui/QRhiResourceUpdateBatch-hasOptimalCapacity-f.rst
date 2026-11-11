.. sip:method-description::
    :status: todo
    :pysig: c506ff134babdd6e68ab3e6350e95305
    :realsig: () const
    :digest: 865f78c239f3ec699e6de5a83e2c6282

Returns true until the number of buffer and texture operations enqueued onto this batch is below a reasonable limit.

The return value is false when the number of buffer and/or texture operations added to this batch have reached, or are about to reach, a certain limit. The batch is fully functional afterwards as well, but may need to allocate additional memory. Therefore, a renderer that collects lots of buffer and texture updates in a single batch when preparing a frame may want to consider :sip:ref:`~PyQt6.QtGui.QRhiCommandBuffer.resourceUpdate` and :sip:ref:`~PyQt6.QtGui.QRhi.nextResourceUpdateBatch` when this function returns false.
