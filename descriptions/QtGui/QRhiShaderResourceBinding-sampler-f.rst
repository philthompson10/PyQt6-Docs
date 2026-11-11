.. sip:method-description::
    :status: todo
    :pysig: 50f125bf9da66a8628d3ae14db7ac3fc
    :realsig: (int, QRhiShaderResourceBinding::StageFlags, QRhiSampler*)
    :digest: 36ef5bba10b6d6f2720b8db8fa9cbffb

Returns a shader resource binding for the given binding number, pipeline stages, and sampler specified by *binding*, *stage*, *sampler*.

**Note:** *sampler* can be null. It is valid to create a :sip:ref:`~PyQt6.QtGui.QRhiShaderResourceBindings` with unspecified resources, but such an object cannot be used with :sip:ref:`~PyQt6.QtGui.QRhiCommandBuffer.setShaderResources`. It is however suitable for creating pipelines. Such a pipeline must then always be used together with another, layout compatible :sip:ref:`~PyQt6.QtGui.QRhiShaderResourceBindings` with resources present passed to :sip:ref:`~PyQt6.QtGui.QRhiCommandBuffer.setShaderResources`.

Arrays of separate samplers are not supported.

This creates a binding for a separate sampler object, whereas :sip:ref:`~PyQt6.QtGui.QRhiShaderResourceBinding.sampledTexture` is suitable for combined image samplers. In Vulkan-compatible GLSL code separate samplers are declared as ``sampler`` as opposed to ``sampler2D``: ``layout(binding = 2) uniform sampler samp;``

With both a ``texture2D`` and ``sampler`` present, they can be used together to sample the texture: ``fragColor = texture(sampler2D(tex, samp), texcoord);``.

**Note:** A shader may not be able to consume more than 16 samplers, depending on the underlying graphics API. This hard limit must be kept in mind in renderer design.

.. seealso:: :sip:ref:`~PyQt6.QtGui.QRhiShaderResourceBinding.texture`.
