.. sip:enum-member-description::
    :status: todo
    :value: 3
    :digest: ef7e2cee45347ca5b4f843d85a7113c6

Remote Bluetooth devices can discover the presence of the local Bluetooth device when performing a limited inquiry. This should be used for locating services that are only made discoverable for a limited period of time. This can speed up discovery between gaming devices, as service discovery can be skipped on devices not in LimitedInquiry mode. In this mode, the device will be connectable and powered on, if required. This mode is is not supported on Android.

**Note:** On macOS, it is not possible to set the :sip:ref:`~PyQt6.QtBluetooth.QBluetoothLocalDevice.hostMode`. The reported host modes are limited to HostPoweredOff and HostConnectable.

**Note:** On Windows, it is not possible to set the :sip:ref:`~PyQt6.QtBluetooth.QBluetoothLocalDevice.hostMode` to HostDiscoverable or HostDiscoverableLimitedInquiry. Using these modes is equivalent to HostConnectable.

**Note:** Starting from Android 13 (API level 33) the HostPoweredOff state relies on non-public Android API as the public one has been deprecated, see (`disable() <https://developer.android.com/reference/android/bluetooth/BluetoothAdapter#disable()>`_). This may change in a future version of Android.

**Note:** At least on Android 12 the device's Bluetooth visibility setting may dictate the result of setting either HostDiscoverable or HostConnectable. For example if the visibility is set *off*, it may not be possible to enter the HostDiscoverable mode, but HostConnectable will be used instead. This may change in future version of Android.
