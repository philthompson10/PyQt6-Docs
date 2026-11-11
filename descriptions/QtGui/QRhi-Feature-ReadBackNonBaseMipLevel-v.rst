.. sip:enum-member-description::
    :status: todo
    :value: 20
    :digest: f838364720d5939a855952fc17be4faf

Indicates that specifying a mip level other than 0 is supported when reading back texture contents. When not supported, specifying a non-zero level in :sip:ref:`~PyQt6.QtGui.QRhiReadbackDescription` leads to returning an all-zero image. In practice this feature will be unsupported with OpenGL ES 2.0.
