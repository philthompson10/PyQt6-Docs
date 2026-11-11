.. sip:method-description::
    :status: todo
    :pysig: c92e646bb2e887489458f93e40b3f0c6
    :realsig: (int, QRhiShaderResourceBinding::StageFlags, QRhiBuffer*)
    :digest: decea96bd2468e07a1788de3d5312e8c

Returns a shader resource binding for the given binding number, pipeline stages, and buffer specified by *binding*, *stage*, and *buf*.

**Note:** When *buf* is not null, it must have been created with :sip:ref:`~PyQt6.QtGui.QRhiBuffer.UsageFlag.UniformBuffer`.

**Note:** *buf* can be null. It is valid to create a :sip:ref:`~PyQt6.QtGui.QRhiShaderResourceBindings` with unspecified resources, but such an object cannot be used with :sip:ref:`~PyQt6.QtGui.QRhiCommandBuffer.setShaderResources`. It is however suitable for creating pipelines. Such a pipeline must then always be used together with another, layout compatible :sip:ref:`~PyQt6.QtGui.QRhiShaderResourceBindings` with resources present passed to :sip:ref:`~PyQt6.QtGui.QRhiCommandBuffer.setShaderResources`.

**Note:** If the size of *buf* exceeds the limit reported for :sip:ref:`~PyQt6.QtGui.QRhi.ResourceLimit.MaxUniformBufferRange`, unexpected errors may occur.
