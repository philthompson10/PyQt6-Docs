.. sip:method-description::
    :status: todo
    :pysig: 67c1c54610b028ed5ab2826bb8b1da58
    :realsig: (int, QRhiShaderResourceBinding::StageFlags, int, const QRhiShaderResourceBinding::TextureAndSampler*)
    :digest: c0957f1e18cc397a834d20bd1d2696ad

Returns a shader resource binding for the given binding number, pipeline stages, and the array of texture-sampler pairs specified by *binding*, *stage*, *count*, and *texSamplers*.

**Note:** *count* must be at least 1, and not larger than 16.

**Note:** When *count* is 1, this function is equivalent to :sip:ref:`~PyQt6.QtGui.QRhiShaderResourceBinding.sampledTexture`.

This function is relevant when arrays of combined image samplers are involved. For example, in GLSL ``layout(binding = 5) uniform sampler2D shadowMaps[8];`` declares an array of combined image samplers. The application is then expected provide a :sip:ref:`~PyQt6.QtGui.QRhiShaderResourceBinding` for binding point 5, set up by calling this function with *count* set to 8 and a valid texture and sampler for each element of the array.

**Warning:** All elements of the array must be specified. With the above example, the only valid, portable approach is calling this function with a *count* of 8. Additionally, all :sip:ref:`~PyQt6.QtGui.QRhiTexture` and :sip:ref:`~PyQt6.QtGui.QRhiSampler` instances must be valid, meaning nullptr is not an accepted value. This is due to some of the underlying APIs, such as, Vulkan, that require a valid image and sampler object for each element in descriptor arrays. Applications are advised to provide "dummy" samplers and textures if some array elements are not relevant (due to not being accessed in the shader).

**Note:** *texSamplers* can be null. It is valid to create a :sip:ref:`~PyQt6.QtGui.QRhiShaderResourceBindings` with unspecified resources, but such an object cannot be used with :sip:ref:`~PyQt6.QtGui.QRhiCommandBuffer.setShaderResources`. It is however suitable for creating pipelines. Such a pipeline must then always be used together with another, layout compatible :sip:ref:`~PyQt6.QtGui.QRhiShaderResourceBindings` with resources present passed to :sip:ref:`~PyQt6.QtGui.QRhiCommandBuffer.setShaderResources`.

.. seealso:: :sip:ref:`~PyQt6.QtGui.QRhiShaderResourceBinding.sampledTexture`.
