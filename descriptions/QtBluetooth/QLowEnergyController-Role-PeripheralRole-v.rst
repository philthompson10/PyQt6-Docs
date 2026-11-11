.. sip:enum-member-description::
    :status: todo
    :value: 1
    :digest: 8e780641ef666075de6be410c23e5ab2

The controller can be used to advertise services and handle incoming connections and client requests, acting as a GATT server. A remote device connected to the controller is in the central role.

**Note:** The peripheral role is not supported on Windows. In addition on Linux, handling the "Signed Write" ATT command on the server side requires BlueZ 5 and kernel version 3.7 or newer.
