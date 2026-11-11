.. sip:enum-description::
    :status: todo
    :digest: 60c3f6390dc5c971192d27248a9ca7b2

This enumerated type describes the range of years (in the Gregorian calendar) representable by :sip:ref:`~PyQt6.QtCore.QDateTime`:

The exact first and last representable datetimes fall within these years and depend on the :sip:ref:`~PyQt6.QtCore.QDateTime.timeRepresentation` used. They can be determined by passing suitable values to :sip:ref:`~PyQt6.QtCore.QDateTime.fromMSecsSinceEpoch`.

All dates strictly between these two years are also representable. Note, however, that the Gregorian Calendar has no year zero.

**Note:** :sip:ref:`~PyQt6.QtCore.QDate` can describe dates in a wider range of years. For most purposes, this makes little difference, as the range of years that :sip:ref:`~PyQt6.QtCore.QDateTime` can support reaches 292 million years either side of 1970.

.. seealso:: :sip:ref:`~PyQt6.QtCore.QDateTime.isValid`, :sip:ref:`~PyQt6.QtCore.QDate`.
