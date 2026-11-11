.. sip:method-description::
    :status: todo
    :pysig: fa47716856aaf35d1187fb29f09b27e4
    :realsig: (int,int,int) const
    :digest: a4307da7f2507d6250c75c246d3b213b

Converts a year, month, and day to a :sip:ref:`~PyQt6.QtCore.QDate`.

The *year*, *month*, and *day* may be passed as separate numbers or packaged together as the members of *parts*. Returns a :sip:ref:`~PyQt6.QtCore.QDate` with the given year, month, and day of the month in this calendar, if there is one. Otherwise, including the case where any of the values is QCalendar::Unspecified, returns a :sip:ref:`~PyQt6.QtCore.QDate` whose isNull() is true. If the date represented falls outside :sip:ref:`~PyQt6.QtCore.QDate`'s supported range, the returned :sip:ref:`~PyQt6.QtCore.QDate`'s isValid() shall be false.

.. seealso:: :sip:ref:`~PyQt6.QtCore.QCalendar.isDateValid`, :sip:ref:`~PyQt6.QtCore.QCalendar.partsFromDate`.
