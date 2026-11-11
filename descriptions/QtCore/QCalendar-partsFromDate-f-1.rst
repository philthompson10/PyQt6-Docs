.. sip:method-description::
    :status: todo
    :pysig: c6181a39672e728689e710853d41f30a
    :realsig: (QDate) const
    :digest: 8cd8b15dbb1bfb47dce2c5ba00435766

Converts a :sip:ref:`~PyQt6.QtCore.QDate` to a year, month, and day of the month.

The returned structure's isValid() shall be false if the calendar is unable to represent the given *date* (or its year would be outside the range that ``int`` can represent). Otherwise its year, month, and day members record the so-named parts of its representation.

.. seealso:: :sip:ref:`~PyQt6.QtCore.QCalendar.dateFromParts`, :sip:ref:`~PyQt6.QtCore.QCalendar.isProleptic`, :sip:ref:`~PyQt6.QtCore.QCalendar.hasYearZero`.
