.. sip:method-description::
    :status: todo
    :pysig: a589a9a9554d10c43c6511be4abefae9
    :realsig: (QRhi::EndFrameFlags)
    :digest: d627bb415c9deb3730cd04732c369155

Ends, submits, and potentially waits for the offscreen frame.

Unlike :sip:ref:`~PyQt6.QtGui.QRhi.endFrame`, this function will block and wait for completion of the GPU-side work when there are active buffer or texture readbacks.

*flags* is not currently used.

.. seealso:: :sip:ref:`~PyQt6.QtGui.QRhi.beginOffscreenFrame`.
