.. sip:method-description::
    :status: todo
    :pysig: 0e9d58b7b5d7645c2f9f24bdefac665f
    :realsig: (int, QRhiShaderResourceBinding::StageFlags, QRhiBuffer*, quint32)
    :digest: 2018db7a2b787204e7d2f8e4638e0fc0

Returns a shader resource binding for the given binding number, pipeline stages, and buffer specified by *binding*, *stage*, and *buf*. The uniform buffer is assumed to have dynamic offset. The dynamic offset can be specified in :sip:ref:`~PyQt6.QtGui.QRhiCommandBuffer.setShaderResources`, thus allowing using varying offset values without creating new bindings for the buffer. The size of the bound region is specified by *size*. Like with non-dynamic offsets, ``offset + size`` cannot exceed the size of *buf*.

**Note:** When *buf* is not null, it must have been created with :sip:ref:`~PyQt6.QtGui.QRhiBuffer.UsageFlag.UniformBuffer`.

**Note:** *buf* can be null. It is valid to create a :sip:ref:`~PyQt6.QtGui.QRhiShaderResourceBindings` with unspecified resources, but such an object cannot be used with :sip:ref:`~PyQt6.QtGui.QRhiCommandBuffer.setShaderResources`. It is however suitable for creating pipelines. Such a pipeline must then always be used together with another, layout compatible :sip:ref:`~PyQt6.QtGui.QRhiShaderResourceBindings` with resources present passed to :sip:ref:`~PyQt6.QtGui.QRhiCommandBuffer.setShaderResources`.

**Note:** If *size* exceeds the limit reported for :sip:ref:`~PyQt6.QtGui.QRhi.ResourceLimit.MaxUniformBufferRange`, unexpected errors may occur.
