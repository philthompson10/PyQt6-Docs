.. sip:method-description::
    :status: todo
    :pysig: 701e3b3003ec0691dbea36dc1558e3e5
    :realsig: (const QDateTime&) const
    :digest: f5b67e3480e46c62f6c70a6c993fc8e2

Returns the number of milliseconds from this datetime to the *other* datetime.

Before performing the comparison, the two datetimes are converted to :sip:ref:`~PyQt6.QtCore.Qt.TimeSpec.UTC` to ensure that the result is correct if daylight-saving (DST) applies to one of the two datetimes and but not the other.

If the *other* datetime is earlier than this datetime, the value returned is negative. Returns 0 if either datetime is invalid.

.. seealso:: :sip:ref:`~PyQt6.QtCore.QDateTime.addMSecs`, :sip:ref:`~PyQt6.QtCore.QDateTime.daysTo`, :sip:ref:`~PyQt6.QtCore.QTime.msecsTo`.
