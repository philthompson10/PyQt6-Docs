.. sip:enum-member-description::
    :status: todo
    :value: 9
    :digest: 217feae938b3af4e3386992967706c87

Indicates that effective index buffer offsets (``indexOffset + firstIndex \* indexComponentSize``) that are not 4 byte aligned are supported. When not supported, attempting to issue a :sip:ref:`~PyQt6.QtGui.QRhiCommandBuffer.drawIndexed` with a non-aligned effective offset may lead to unspecified behavior. Relevant in particular for Metal, where this will be reported as unsupported.
