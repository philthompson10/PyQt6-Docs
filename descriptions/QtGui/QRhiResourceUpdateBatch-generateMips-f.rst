.. sip:method-description::
    :status: todo
    :pysig: e977319e0a3045bbe1ad2e3bedbc857a
    :realsig: (QRhiTexture*)
    :digest: b5add20af00b8dbd021ab9d32b1bcfdb

Enqueues a mipmap generation operation for the specified texture *tex*.

2D and cube textures are supported. 1D and 3D textures are supported when the :sip:ref:`~PyQt6.QtGui.QRhi.Feature.OneDimensionalTextureMipmaps` or :sip:ref:`~PyQt6.QtGui.QRhi.Feature.ThreeDimensionalTextureMipmaps` feature is reported as supported, respectively.

**Note:** The texture must be created with :sip:ref:`~PyQt6.QtGui.QRhiTexture.Flag.MipMapped` and :sip:ref:`~PyQt6.QtGui.QRhiTexture.Flag.UsedWithGenerateMips`.

**Warning:** :sip:ref:`~PyQt6.QtGui.QRhi` cannot guarantee that mipmaps can be generated for all supported texture formats. For example, :sip:ref:`~PyQt6.QtGui.QRhiTexture.Format.RGBA32F` is not a ``filterable`` format in OpenGL ES 3.0 and Metal on iOS, and therefore the mipmap generation request may fail. RGBA8 and RGBA16F are typically filterable, so it is recommended to use these formats when mipmap generation is desired.
