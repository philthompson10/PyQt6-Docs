.. sip:method-description::
    :status: todo
    :pysig: 00df7b0bd472813acad7a315c322a77d
    :realsig: (int, QRhiShaderResourceBinding::StageFlags, QRhiBuffer*, quint32, quint32)
    :digest: fa998047eaf6bc35fcd2b08b046121e0

Returns a shader resource binding for the given binding number, pipeline stages, and buffer specified by *binding*, *stage*, and *buf*. This overload binds a region only, as specified by *offset* and *size*.

**Note:** It is up to the user to ensure the offset is aligned to :sip:ref:`~PyQt6.QtGui.QRhi.ubufAlignment`.

**Note:** *size* must be greater than 0.

**Note:** When *buf* is not null, it must have been created with :sip:ref:`~PyQt6.QtGui.QRhiBuffer.UsageFlag.UniformBuffer`.

**Note:** *buf* can be null. It is valid to create a :sip:ref:`~PyQt6.QtGui.QRhiShaderResourceBindings` with unspecified resources, but such an object cannot be used with :sip:ref:`~PyQt6.QtGui.QRhiCommandBuffer.setShaderResources`. It is however suitable for creating pipelines. Such a pipeline must then always be used together with another, layout compatible :sip:ref:`~PyQt6.QtGui.QRhiShaderResourceBindings` with resources present passed to :sip:ref:`~PyQt6.QtGui.QRhiCommandBuffer.setShaderResources`.

**Note:** If *size* exceeds the limit reported for :sip:ref:`~PyQt6.QtGui.QRhi.ResourceLimit.MaxUniformBufferRange`, unexpected errors may occur.
