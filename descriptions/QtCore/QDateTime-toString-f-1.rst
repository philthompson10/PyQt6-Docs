.. sip:method-description::
    :status: todo
    :pysig: 3eca7e6a9b2db1121534f22b513acdcd
    :realsig: (const QString&, QCalendar) const
    :digest: f3824a82fb950df9a4a8ac60645f6e9b

Returns the datetime as a string. The *format* parameter determines the format of the result string. If *cal* is supplied, it determines the calendar used to represent the date; it defaults to Gregorian. Prior to Qt 5.14, there was no *cal* parameter and the Gregorian calendar was always used. See :sip:ref:`~PyQt6.QtCore.QTime.toString` and :sip:ref:`~PyQt6.QtCore.QDate.toString` for the supported specifiers for time and date, respectively, in the *format* parameter.

Any non-empty sequence of characters enclosed in single quotes will be included verbatim in the output string (stripped of the quotes), even if it contains formatting characters. Two consecutive single quotes ("''") are replaced by a single quote in the output, rather than starting or ending a verbatim sequence. All other characters in the format string are included verbatim in the output string.

Formats without separators (e.g. "ddMM") are supported but must be used with care, as the resulting strings aren't always reliably readable (e.g. if "dM" produces "212" it could mean either the 2nd of December or the 21st of February).

Example format strings (assumed that the :sip:ref:`~PyQt6.QtCore.QDateTime` is 21 May 2001 14:13:09.120):

+---------------+---------------+
| Format        | Result        |
+===============+===============+
| dd.MM.yyyy    | 21.05.2001    |
+---------------+---------------+
| ddd MMMM d yy | Tue May 21 01 |
+---------------+---------------+
| hh:mm:ss.zzz  | 14:13:09.120  |
+---------------+---------------+
| hh:mm:ss.z    | 14:13:09.12   |
+---------------+---------------+
| h:m:s ap      | 2:13:9 pm     |
+---------------+---------------+

If the datetime is invalid, an empty string will be returned.

**Note:** Day and month names as well as AM/PM indicators are given in English (C locale). To get localized month and day names and localized forms of AM/PM, use :sip:ref:`~PyQt6.QtCore.QLocale.system`.toDateTime().

.. seealso:: :sip:ref:`~PyQt6.QtCore.QDateTime.fromString`, :sip:ref:`~PyQt6.QtCore.QDate.toString`, :sip:ref:`~PyQt6.QtCore.QTime.toString`, :sip:ref:`~PyQt6.QtCore.QLocale.toString`.
