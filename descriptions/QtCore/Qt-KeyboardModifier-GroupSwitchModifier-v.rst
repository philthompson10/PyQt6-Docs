.. sip:enum-member-description::
    :status: todo
    :value: 0x40000000
    :digest: 25e6898468757d8053ba2500cfe4373a

X11 only (unless activated on Windows by a command line argument). A Mode_switch key on the keyboard is pressed.

**Note:** On macOS, the ``ControlModifier`` value corresponds to the Command keys on the keyboard, and the ``MetaModifier`` value corresponds to the Control keys. The ``KeypadModifier`` value will also be set when an arrow key is pressed as the arrow keys are considered part of the keypad.

**Note:** On Windows Keyboards, Qt::MetaModifier and :sip:ref:`~PyQt6.QtCore.Qt.Key.Key_Meta` are mapped to the Windows key.
