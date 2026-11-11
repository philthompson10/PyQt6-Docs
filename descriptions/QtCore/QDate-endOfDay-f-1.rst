.. sip:method-description::
    :status: todo
    :pysig: 2d10d6c7e48af6be6801c538cf3f30ce
    :realsig: (Qt::TimeSpec,int) const
    :digest: 6921ce19840e094fdc680f64d3b69aa0

Use ``endOfDay(const QTimeZone &)`` instead.

Returns the end-moment of the day.

When a day ends depends on a how time is described: each day starts and ends earlier for those with higher offsets from UTC and later for those with lower offsets from UTC. The time representation to use can be specified either by a *spec* and *offsetSeconds* (ignored unless *spec* is Qt::OffsetSeconds) or by a time zone.

Usually, the end of the day is one millisecond before the midnight, 24:00: however, if a local time transition causes the given date to skip over that moment (e.g. a DST spring-forward skipping over 23:00 and the following hour), the actual latest time in the day is returned.

When *spec* is :sip:ref:`~PyQt6.QtCore.Qt.TimeSpec.OffsetFromUTC`, *offsetSeconds* gives the implied zone's offset from UTC. As UTC and such zones have no transitions, the end of the day is :sip:ref:`~PyQt6.QtCore.QTime`\ (23, 59, 59, 999) in these cases.

In the rare case of a date that was entirely skipped (this happens when a zone east of the international date-line switches to being west of it), the return shall be invalid. Passing :sip:ref:`~PyQt6.QtCore.Qt.TimeSpec.TimeZone` as *spec* (instead of passing a :sip:ref:`~PyQt6.QtCore.QTimeZone`) will also produce an invalid result, as shall dates that end outside the range representable by :sip:ref:`~PyQt6.QtCore.QDateTime`.
