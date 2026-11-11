.. sip:method-description::
    :status: todo
    :pysig: f4d97c6746f10ab569f47bd67f8ad8e1
    :realsig: (int, QRhiShaderResourceBinding::StageFlags, QRhiTexture*)
    :digest: dc5f8bf0e366009dd966f9dd61c1562e

Returns a shader resource binding for the given binding number, pipeline stages, and texture specified by *binding*, *stage*, *tex*.

**Note:** This function is equivalent to calling :sip:ref:`~PyQt6.QtGui.QRhiShaderResourceBinding.textures` with a ``count`` of 1.

**Note:** *tex* can be null. It is valid to create a :sip:ref:`~PyQt6.QtGui.QRhiShaderResourceBindings` with unspecified resources, but such an object cannot be used with :sip:ref:`~PyQt6.QtGui.QRhiCommandBuffer.setShaderResources`. It is however suitable for creating pipelines. Such a pipeline must then always be used together with another, layout compatible :sip:ref:`~PyQt6.QtGui.QRhiShaderResourceBindings` with resources present passed to :sip:ref:`~PyQt6.QtGui.QRhiCommandBuffer.setShaderResources`.

This creates a binding for a separate texture (image) object, whereas :sip:ref:`~PyQt6.QtGui.QRhiShaderResourceBinding.sampledTexture` is suitable for combined image samplers. In Vulkan-compatible GLSL code separate textures are declared as ``texture2D`` as opposed to ``sampler2D``: ``layout(binding = 1) uniform texture2D tex;``

**Note:** A shader may not be able to consume more than 16 textures, depending on the underlying graphics API. This hard limit must be kept in mind in renderer design. This does not apply to texture arrays which consume a single binding point (shader register) and can contain 256-2048 textures, depending on the underlying graphics API. Arrays of textures (see :sip:ref:`~PyQt6.QtGui.QRhiShaderResourceBinding.sampledTextures`) are however no different in this regard than using the same number of individual textures.

.. seealso:: :sip:ref:`~PyQt6.QtGui.QRhiShaderResourceBinding.textures`, :sip:ref:`~PyQt6.QtGui.QRhiShaderResourceBinding.sampler`.
