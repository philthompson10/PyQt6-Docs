.. sip:enum-member-description::
    :status: todo
    :value: 1 << 2
    :digest: 64065d14ed836828d7fbe8dbba71fd47

Indicates that the contents of the depth texture does not need to be written out. Relevant only when a :sip:ref:`~PyQt6.QtGui.QRhiTexture`, not :sip:ref:`~PyQt6.QtGui.QRhiRenderBuffer`, is used as the depth-stencil buffer, because for :sip:ref:`~PyQt6.QtGui.QRhiRenderBuffer` this is implicit. When a depthResolveTexture is set, the flag is not relevant, because the behavior is then as if the flag was set. This enum value is introduced in Qt 6.8.
