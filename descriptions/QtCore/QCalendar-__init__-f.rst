.. sip:method-description::
    :status: todo
    :pysig: d41d8cd98f00b204e9800998ecf8427e
    :realsig: ()
    :digest: 2e314deffdf472c4572e7e28f22e5edb

Constructs a calendar object.

The choice of calendar to use may be indicated by *system*, using the enumeration :sip:ref:`~PyQt6.QtCore.QCalendar.System`, or by *name*, using a string (either Unicode or Latin 1). Construction by name may depend on an instance of the given calendar being constructed by other means first. With no argument, the default constructor returns the Gregorian calendar.

**Note:** In Qt versions before 6.4, the constructor by *name* accepted only QStringView and QLatin1String, not QAnyStringView.

.. seealso:: :sip:ref:`~PyQt6.QtCore.QCalendar`, :sip:ref:`~PyQt6.QtCore.QCalendar.System.System`, isValid().
