.. sip:method-description::
    :status: todo
    :pysig: 10af81a042890d7d71ec29fba47e8425
    :realsig: (int, QRhiShaderResourceBinding::StageFlags, QRhiTexture*, QRhiSampler*)
    :digest: be2ff2fa489d8821b7e70c0a49c01ae7

Returns a shader resource binding for the given binding number, pipeline stages, texture, and sampler specified by *binding*, *stage*, *tex*, *sampler*.

**Note:** This function is equivalent to calling :sip:ref:`~PyQt6.QtGui.QRhiShaderResourceBinding.sampledTextures` with a ``count`` of 1.

**Note:** *tex* and *sampler* can be null. It is valid to create a :sip:ref:`~PyQt6.QtGui.QRhiShaderResourceBindings` with unspecified resources, but such an object cannot be used with :sip:ref:`~PyQt6.QtGui.QRhiCommandBuffer.setShaderResources`. It is however suitable for creating pipelines. Such a pipeline must then always be used together with another, layout compatible :sip:ref:`~PyQt6.QtGui.QRhiShaderResourceBindings` with resources present passed to :sip:ref:`~PyQt6.QtGui.QRhiCommandBuffer.setShaderResources`.

**Note:** A shader may not be able to consume more than 16 textures/samplers, depending on the underlying graphics API. This hard limit must be kept in mind in renderer design. This does not apply to texture arrays which consume a single binding point (shader register) and can contain 256-2048 textures, depending on the underlying graphics API. Arrays of textures (see :sip:ref:`~PyQt6.QtGui.QRhiShaderResourceBinding.sampledTextures`) are however no different in this regard than using the same number of individual textures.

.. seealso:: :sip:ref:`~PyQt6.QtGui.QRhiShaderResourceBinding.sampledTextures`.
