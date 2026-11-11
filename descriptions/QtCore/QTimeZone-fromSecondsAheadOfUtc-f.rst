.. sip:method-description::
    :status: todo
    :pysig: c6cd2caa6d3eaaa8f56f5e0083c10333
    :realsig: (int)
    :digest: b54be57e1f19c0146d6433902ea921bb

Returns a time representation at a fixed *offset*, in seconds, ahead of UTC.

The *offset* from UTC must be in the range -16 hours to +16 hours otherwise an invalid time zone will be returned. The returned :sip:ref:`~PyQt6.QtCore.QTimeZone` is a lightweight time representation, not a time zone (backed by system-supplied or standard data).

If the offset is 0, the :sip:ref:`~PyQt6.QtCore.QTimeZone.timeSpec` of the returned instance will be :sip:ref:`~PyQt6.QtCore.Qt.TimeSpec.UTC`. Otherwise, if *offset* is valid, :sip:ref:`~PyQt6.QtCore.QTimeZone.timeSpec` is :sip:ref:`~PyQt6.QtCore.Qt.TimeSpec.OffsetFromUTC`. An invalid time zone, when returned, has :sip:ref:`~PyQt6.QtCore.Qt.TimeSpec.TimeZone` as its :sip:ref:`~PyQt6.QtCore.QTimeZone.timeSpec`.

.. seealso:: QTimeZone(int), :sip:ref:`~PyQt6.QtCore.QTimeZone.asBackendZone`, :sip:ref:`~PyQt6.QtCore.QTimeZone.fixedSecondsAheadOfUtc`, MinUtcOffsetSecs, MaxUtcOffsetSecs.
