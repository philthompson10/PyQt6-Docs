.. sip:method-description::
    :status: todo
    :pysig: 00df7b0bd472813acad7a315c322a77d
    :realsig: (int, QRhiShaderResourceBinding::StageFlags, QRhiBuffer*, quint32, quint32)
    :digest: 4c36b2533fb98c5d8d1e560c087690e4

Returns a shader resource binding for a read-only storage buffer with the given *binding* number and pipeline *stage*. This overload binds a region only, as specified by *offset* and *size*.

**Note:** When *buf* is not null, must have been created with :sip:ref:`~PyQt6.QtGui.QRhiBuffer.UsageFlag.StorageBuffer`.

**Note:** *buf* can be null. It is valid to create a :sip:ref:`~PyQt6.QtGui.QRhiShaderResourceBindings` with unspecified resources, but such an object cannot be used with :sip:ref:`~PyQt6.QtGui.QRhiCommandBuffer.setShaderResources`. It is however suitable for creating pipelines. Such a pipeline must then always be used together with another, layout compatible :sip:ref:`~PyQt6.QtGui.QRhiShaderResourceBindings` with resources present passed to :sip:ref:`~PyQt6.QtGui.QRhiCommandBuffer.setShaderResources`.

**Note:** Buffer load/store is only guaranteed to be available within a compute pipeline. While some backends may support using these resources in a graphics pipeline as well, this is not universally supported, and even when it is, unexpected problems may arise when it comes to barriers and synchronization. Therefore, avoid using such resources with shaders other than compute.
