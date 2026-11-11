.. sip:method-description::
    :status: todo
    :pysig: 701e3b3003ec0691dbea36dc1558e3e5
    :realsig: (const QDateTime&) const
    :digest: 5f81d2e25cfe1e4dfa5cf939068374c4

Returns the number of seconds from this datetime to the *other* datetime.

Before performing the comparison, the two datetimes are converted to :sip:ref:`~PyQt6.QtCore.Qt.TimeSpec.UTC` to ensure that the result is correct if daylight-saving (DST) applies to one of the two datetimes but not the other.

If the *other* datetime is earlier than this datetime, the value returned is negative. Returns 0 if either datetime is invalid.

Example:

.. literalinclude:: ../../../snippets/qtbase-src-corelib-doc-snippets-code-src_corelib_time_qdatetime.py
    :lines: 132-134

.. seealso:: :sip:ref:`~PyQt6.QtCore.QDateTime.addSecs`, :sip:ref:`~PyQt6.QtCore.QDateTime.daysTo`, :sip:ref:`~PyQt6.QtCore.QTime.secsTo`.
