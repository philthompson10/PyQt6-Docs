.. sip:method-description::
    :status: todo
    :pysig: 9fd787b90c99a23637f0e8f90afb9680
    :realsig: (double,char,int)
    :digest: ca48465db1ff0ef52c85ab04d16f989f

Represent the floating-point number *n* as text.

Sets this byte array to a string representing *n*, with a given *format* and *precision* (with the same meanings as for QLocale::toString(double, char, int)), and returns a reference to this byte array.

.. seealso:: :sip:ref:`~PyQt6.QtCore.QByteArray.toDouble`, :sip:ref:`~PyQt6.QtCore.QLocale.FloatingPointPrecisionOption`.
