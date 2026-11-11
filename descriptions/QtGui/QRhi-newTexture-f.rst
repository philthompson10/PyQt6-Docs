.. sip:method-description::
    :status: todo
    :pysig: db2ca657d36e75bcbd9b892fdd180b75
    :realsig: (QRhiTexture::Format, const QSize&, int, QRhiTexture::Flags)
    :digest: 283873acd7803898aaafb273af5b7d96

Returns a new 1D or 2D texture with the specified *format*, *pixelSize*, *sampleCount*, and *flags*.

A 1D texture must have :sip:ref:`~PyQt6.QtGui.QRhiTexture.Flag.OneDimensional` set in *flags*. This function will implicitly set this flag if the *pixelSize* height is 0.

**Note:** *format* specifies the requested internal and external format, meaning the data to be uploaded to the texture will need to be in a compatible format, while the native texture may (but is not guaranteed to, in case of OpenGL at least) use this format internally.

**Note:** 1D textures are only functional when the :sip:ref:`~PyQt6.QtGui.QRhi.Feature.OneDimensionalTextures` feature is reported as supported at run time. Further, mipmaps on 1D textures are only functional when the :sip:ref:`~PyQt6.QtGui.QRhi.Feature.OneDimensionalTextureMipmaps` feature is reported at run time.

.. seealso:: :sip:ref:`~PyQt6.QtGui.QRhiResource.destroy`.
