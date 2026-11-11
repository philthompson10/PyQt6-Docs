.. sip:enum-member-description::
    :status: todo
    :value: 0x01
    :digest: c9905c65299ee6127fcebdf4daacda77

Specifies that there will be a call to :sip:ref:`~PyQt6.QtGui.QRhiCommandBuffer.beginExternal` in this pass. Some backends, Vulkan in particular, will fail if this flag is not set and :sip:ref:`~PyQt6.QtGui.QRhiCommandBuffer.beginExternal` is still called.
