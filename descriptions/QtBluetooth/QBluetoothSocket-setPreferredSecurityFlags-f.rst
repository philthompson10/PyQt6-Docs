.. sip:method-description::
    :status: todo
    :pysig: 76b1d76b58b3fa384e0af90fb23670ee
    :realsig: (QBluetooth::SecurityFlags)
    :digest: 0c39ee42fa4deb3835331f495728fb3e

Sets the preferred security parameter for the connection attempt to *flags*. This value is incorporated when calling :sip:ref:`~PyQt6.QtBluetooth.QBluetoothSocket.connectToService`. Therefore it is required to reconnect to change this parameter for an existing connection.

On the Linux BlueZ backend, the flags are mapped to kernel security levels:

* :sip:ref:`~PyQt6.QtBluetooth.QBluetooth.Security.Authorization` maps to ``BT_SECURITY_LOW``;

* :sip:ref:`~PyQt6.QtBluetooth.QBluetooth.Security.Encryption` maps to ``BT_SECURITY_MEDIUM``;

* :sip:ref:`~PyQt6.QtBluetooth.QBluetooth.Security.Secure` maps to ``BT_SECURITY_HIGH``;

* :sip:ref:`~PyQt6.QtBluetooth.QBluetooth.Security.Authentication` is not used by the kernel and **is ignored**.

The default value is :sip:ref:`~PyQt6.QtBluetooth.QBluetooth.Security.Authorization`.

On Linux with the BlueZ D-Bus backend and on Windows, this flag is not supported and ignored.

On macOS, this value is ignored as the platform does not permit access to the security parameter of the socket. By default the platform prefers secure/encrypted connections though and therefore this function always returns :sip:ref:`~PyQt6.QtBluetooth.QBluetooth.Security.Secure`.

Android only supports two levels of security (secure and non-secure). If this flag is set to :sip:ref:`~PyQt6.QtBluetooth.QBluetooth.Security.NoSecurity` the socket object will not employ any authentication or encryption. Any other security flag combination will trigger a secure Bluetooth connection. This flag is set to :sip:ref:`~PyQt6.QtBluetooth.QBluetooth.Security.Secure` by default.

**Note:** A secure connection requires a pairing between the two devices. On some platforms, the pairing is automatically initiated during the establishment of the connection. Other platforms require the application to manually trigger the pairing before attempting to connect.

.. seealso:: :sip:ref:`~PyQt6.QtBluetooth.QBluetoothSocket.preferredSecurityFlags`.
