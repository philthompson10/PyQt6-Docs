.. sip:method-description::
    :status: todo
    :pysig: fa7153f7ed1cb6c0fcf2ffb2fac21748
    :realsig: (qint64)
    :digest: 2be289f880ca456e7ce79341a9adb1f8

Sets the size of :sip:ref:`~PyQt6.QtSerialPort.QSerialPort`'s internal write buffer to be *size* bytes.

Sending data over a serial port is relatively slow, so in practice the data is not sent immediately when write() is called. It is first stored in an intermediate buffer and later written in chunks.

Thus, writing too much data, or writing it at a higher rate than the underlying serial port can handle, can make the internal buffer grow. This can eventually cause the application to run out of memory, especially on a device with low memory resources.

This method allows limiting the internal buffer to a certain size. If the next write attempt exceeds the capacity of the buffer, the write() method returns the number of bytes that were actually stored in the buffer. It is the user's responsibility to repeat the write attempt with the rest of the bytes after the bytesWritten() signal is received, or after the :sip:ref:`~PyQt6.QtSerialPort.QSerialPort.waitForBytesWritten` method returns ``true``.

Passing ``0`` to this method means that the write buffer is not limited, and all the data passed to write() is buffered. This is the default.

Passing a negative value has the same effect as passing ``0``.

.. seealso:: :sip:ref:`~PyQt6.QtSerialPort.QSerialPort.writeBufferSize`, write().
