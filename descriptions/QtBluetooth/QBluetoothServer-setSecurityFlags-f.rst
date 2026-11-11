.. sip:method-description::
    :status: todo
    :pysig: 76b1d76b58b3fa384e0af90fb23670ee
    :realsig: (QBluetooth::SecurityFlags)
    :digest: 720c8c9342d97febee2a19eeb30b96d1

Sets the Bluetooth security flags to *security*. This function must be called before calling :sip:ref:`~PyQt6.QtBluetooth.QBluetoothServer.listen`. The Bluetooth link will always be encrypted when using Bluetooth 2.1 devices as encryption is mandatory.

On the Linux BlueZ backend, the flags are mapped to kernel security levels:

* :sip:ref:`~PyQt6.QtBluetooth.QBluetooth.Security.Authorization` maps to ``BT_SECURITY_LOW``;

* :sip:ref:`~PyQt6.QtBluetooth.QBluetooth.Security.Encryption` maps to ``BT_SECURITY_MEDIUM``;

* :sip:ref:`~PyQt6.QtBluetooth.QBluetooth.Security.Secure` maps to ``BT_SECURITY_HIGH``;

* :sip:ref:`~PyQt6.QtBluetooth.QBluetooth.Security.Authentication` is not used by the kernel and **is ignored**.

The default value is :sip:ref:`~PyQt6.QtBluetooth.QBluetooth.Security.Authorization`.

Android only supports two levels of security (secure and non-secure). If this flag is set to :sip:ref:`~PyQt6.QtBluetooth.QBluetooth.Security.NoSecurity` the server object will not employ any authentication or encryption. Any other security flag combination will trigger a secure Bluetooth connection.

On macOS and Windows, security flags are not supported and will be ignored.

.. seealso:: :sip:ref:`~PyQt6.QtBluetooth.QBluetoothServer.securityFlags`.
