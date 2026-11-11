.. sip:method-description::
    :status: todo
    :pysig: 701e3b3003ec0691dbea36dc1558e3e5
    :realsig: (const QDateTime&) const
    :digest: a6d3787446e5271958672041c301b93e

Returns the number of days from this datetime to the *other* datetime.

The number of days is counted as the number of times midnight is reached between this datetime and the *other* datetime. This means that a 10 minute difference from 23:55 to 0:05 the next day counts as one day.

If the *other* datetime is earlier than this datetime, the value returned is negative. If either datetime is invalid, the value is 0.

Example:

.. literalinclude:: ../../../snippets/qtbase-src-corelib-doc-snippets-code-src_corelib_time_qdatetime.py
    :lines: 163-172

.. seealso:: :sip:ref:`~PyQt6.QtCore.QDateTime.addDays`, :sip:ref:`~PyQt6.QtCore.QDateTime.secsTo`, :sip:ref:`~PyQt6.QtCore.QDateTime.msecsTo`.
