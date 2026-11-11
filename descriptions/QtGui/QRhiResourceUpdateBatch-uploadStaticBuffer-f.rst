.. sip:method-description::
    :status: todo
    :pysig: 686990dc5906526578c5aaffa276c07e
    :realsig: (QRhiBuffer*, QByteArray)
    :digest: d41cf20fd47bfa8ed8744a1523798d66

Enqueues updating the entire :sip:ref:`~PyQt6.QtGui.QRhiBuffer` *buf* created with the type :sip:ref:`~PyQt6.QtGui.QRhiBuffer.Type.Immutable` or :sip:ref:`~PyQt6.QtGui.QRhiBuffer.Type.Static`.

*data* is moved into the batch instead of copied with this overload.

*data* size must equal the size of *buf*.
