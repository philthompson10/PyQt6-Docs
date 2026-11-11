.. sip:enum-member-description::
    :status: todo
    :value: 2
    :digest: 1327a831b1086b20afc58fbb3530acc5

Indicates that the data is expected to change frequently. Not recommended for large buffers. Typically backed by host visible memory in 2 copies in order to allow for changing without stalling the graphics pipeline. The double buffering is managed transparently to the applications and is not exposed in the API here in any form. This is the recommended, and, with some backends, the only possible, type for buffers with :sip:ref:`~PyQt6.QtGui.QRhiBuffer.UsageFlag.UniformBuffer` usage.
