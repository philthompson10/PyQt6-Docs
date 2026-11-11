.. sip:method-description::
    :status: todo
    :pysig: b977d4d0807f2f6336d51d86d98ecb90
    :realsig: (QRhiTexture::Format, int, const QSize&, int, QRhiTexture::Flags)
    :digest: 60f3ca38e695362eefe6b8b3206d9e61

Returns a new 1D or 2D texture array with the specified *format*, *arraySize*, *pixelSize*, *sampleCount*, and *flags*.

This function implicitly sets :sip:ref:`~PyQt6.QtGui.QRhiTexture.Flag.TextureArray` in *flags*.

A 1D texture array must have :sip:ref:`~PyQt6.QtGui.QRhiTexture.Flag.OneDimensional` set in *flags*. This function will implicitly set this flag if the *pixelSize* height is 0.

**Note:** Do not confuse texture arrays with arrays of textures. A :sip:ref:`~PyQt6.QtGui.QRhiTexture` created by this function is usable with 1D or 2D array samplers in the shader, for example: ``layout(binding = 1) uniform sampler2DArray texArr;``. Arrays of textures refers to a list of textures that are exposed to the shader via :sip:ref:`~PyQt6.QtGui.QRhiShaderResourceBinding.sampledTextures` and a count > 1, and declared in the shader for example like this: ``layout(binding = 1) uniform sampler2D textures[4];``

**Note:** This is only functional when the :sip:ref:`~PyQt6.QtGui.QRhi.Feature.TextureArrays` feature is reported as supported at run time.

**Note:** 1D textures are only functional when the :sip:ref:`~PyQt6.QtGui.QRhi.Feature.OneDimensionalTextures` feature is reported as supported at run time. Further, mipmaps on 1D textures are only functional when the :sip:ref:`~PyQt6.QtGui.QRhi.Feature.OneDimensionalTextureMipmaps` feature is reported at run time.

.. seealso:: :sip:ref:`~PyQt6.QtGui.QRhi.newTexture`.
