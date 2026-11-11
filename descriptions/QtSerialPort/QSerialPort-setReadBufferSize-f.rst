.. sip:method-description::
    :status: todo
    :pysig: fa7153f7ed1cb6c0fcf2ffb2fac21748
    :realsig: (qint64)
    :digest: b64db6c06482325d7ab1fab5596a3615

Sets the size of :sip:ref:`~PyQt6.QtSerialPort.QSerialPort`'s internal read buffer to be *size* bytes.

If the buffer size is limited to a certain size, :sip:ref:`~PyQt6.QtSerialPort.QSerialPort` will not buffer more than this size of data. The special case of a buffer size of ``0`` means that the read buffer is unlimited and all incoming data is buffered. This is the default.

This option is useful if the data is only read at certain points in time (for instance in a real-time streaming application) or if the serial port should be protected against receiving too much data, which may eventually cause the application to run out of memory.

Passing a negative value disables the internal buffer, effectively blocking any reads.

.. seealso:: :sip:ref:`~PyQt6.QtSerialPort.QSerialPort.readBufferSize`, read().
