.. sip:method-description::
    :status: todo
    :pysig: 464116456943d857ef223b2d24ec328b
    :realsig: (const QString&)
    :digest: b6a5adf4b7e996d44c974a9fad193155

Sets the *name* of the serial port.

The name of the serial port can be passed as either a short name or the long system location if necessary.

**Note:** This function allows setting ports that are not included in the :sip:ref:`~PyQt6.QtSerialPort.QSerialPortInfo.availablePorts`, or where constructing a :sip:ref:`~PyQt6.QtSerialPort.QSerialPortInfo` instance with the name string yields a :sip:ref:`~PyQt6.QtSerialPort.QSerialPortInfo.isNull` object. If that is not a requirement, then use :sip:ref:`~PyQt6.QtSerialPort.QSerialPort.setPort` instead after checking that the name results in a valid :sip:ref:`~PyQt6.QtSerialPort.QSerialPortInfo` object.

.. seealso:: :sip:ref:`~PyQt6.QtSerialPort.QSerialPort.portName`, :sip:ref:`~PyQt6.QtSerialPort.QSerialPortInfo`.
