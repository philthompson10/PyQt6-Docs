.. sip:method-description::
    :status: todo
    :pysig: 9f4da284a36c3d58dd7a7bc569462d38
    :realsig: (QDate) const
    :digest: a2293e62af5d9eb3f5694c61672f1d00

Returns the day of the week number for the given *date*.

Returns zero if the calendar is unable to represent the indicated date. Returns 1 for Monday through 7 for Sunday. Calendars with intercalary days may use other numbers to represent these.

.. seealso:: :sip:ref:`~PyQt6.QtCore.QCalendar.partsFromDate`, :sip:ref:`~PyQt6.QtCore.Qt.DayOfWeek`.
