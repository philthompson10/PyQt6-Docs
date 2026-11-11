.. sip:method-description::
    :status: todo
    :pysig: 3eca7e6a9b2db1121534f22b513acdcd
    :realsig: (const QString&, QCalendar) const
    :digest: c5b0de18d8879790a3592ce4a48850c8

Returns the date as a string. The *format* parameter determines the format of the result string. If *cal* is supplied, it determines the calendar used to represent the date; it defaults to Gregorian. Prior to Qt 5.14, there was no *cal* parameter and the Gregorian calendar was always used.

These expressions may be used in the *format* parameter:

+------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
| Expression | Output                                                                                                                                                                                                |
+============+=======================================================================================================================================================================================================+
| d          | The day as a number without a leading zero (1 to 31)                                                                                                                                                  |
+------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
| dd         | The day as a number with a leading zero (01 to 31)                                                                                                                                                    |
+------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
| ddd        | The abbreviated day name ('Mon' to 'Sun').                                                                                                                                                            |
+------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
| dddd       | The long day name ('Monday' to 'Sunday').                                                                                                                                                             |
+------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
| M          | The month as a number without a leading zero (1 to 12)                                                                                                                                                |
+------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
| MM         | The month as a number with a leading zero (01 to 12)                                                                                                                                                  |
+------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
| MMM        | The abbreviated month name ('Jan' to 'Dec').                                                                                                                                                          |
+------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
| MMMM       | The long month name ('January' to 'December').                                                                                                                                                        |
+------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
| yy         | The year as a two digit number (00 to 99)                                                                                                                                                             |
+------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
| yyyy       | The full year as a number, padded if necessary to at least four digits. If the year is negative, a minus sign is prepended. If a positive year needs more than four digits, a plus sign is prepended. |
+------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+

Any non-empty sequence of characters enclosed in single quotes will be included verbatim in the output string (stripped of the quotes), even if it contains formatting characters. Two consecutive single quotes ("''") are replaced by a single quote in the output, rather than starting or ending a verbatim sequence. All other characters in the format string are included verbatim in the output string.

Formats without separators (e.g. "ddMM") are supported but must be used with care, as the resulting strings aren't always reliably readable (e.g. if "dM" produces "212" it could mean either the 2nd of December or the 21st of February).

Example format strings (assuming that the :sip:ref:`~PyQt6.QtCore.QDate` is the 20 July 1969):

+-------------------+-------------------+
| Format            | Result            |
+===================+===================+
| dd.MM.yyyy        | 20.07.1969        |
+-------------------+-------------------+
| ddd MMMM d yy     | Sun July 20 69    |
+-------------------+-------------------+
| 'The day is' dddd | The day is Sunday |
+-------------------+-------------------+

If the datetime is invalid, an empty string will be returned.

**Note:** Day and month names are given in English (C locale). To get localized month and day names, use :sip:ref:`~PyQt6.QtCore.QLocale.system`.toString().

**Note:** If a format character is repeated more times than the longest expression in the table above using it, this part of the format will be read as several expressions with no separator between them; the longest above, possibly repeated as many times as there are copies of it, ending with a residue that may be a shorter expression. Thus ``'MMMMMMMMMM'`` for a date in May will contribute ``"MayMay05"`` to the output.

.. seealso:: :sip:ref:`~PyQt6.QtCore.QDate.fromString`, :sip:ref:`~PyQt6.QtCore.QDateTime.toString`, :sip:ref:`~PyQt6.QtCore.QTime.toString`, :sip:ref:`~PyQt6.QtCore.QLocale.toString`.
