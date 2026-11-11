.. sip:method-description::
    :status: todo
    :pysig: 321ccaeab979a21e197a96919ce67a4e
    :realsig: (QRhiTexture::Format, int, int, int, int, QRhiTexture::Flags)
    :digest: a9a9525f12a0ef53eba3dff9d355e76c

Returns a new 1D, 2D or 3D texture with the specified *format*, *width*, *height*, *depth*, *sampleCount*, and *flags*.

This overload is suitable for 3D textures because it allows specifying *depth*. A 3D texture must have :sip:ref:`~PyQt6.QtGui.QRhiTexture.Flag.ThreeDimensional` set in *flags*, but using this overload that can be omitted because the flag is set implicitly whenever *depth* is greater than 0. For 1D, 2D and cube textures *depth* should be set to 0.

A 1D texture must have :sip:ref:`~PyQt6.QtGui.QRhiTexture.Flag.OneDimensional` set in *flags*. This overload will implicitly set this flag if both *height* and *depth* are 0.

**Note:** 3D textures are only functional when the :sip:ref:`~PyQt6.QtGui.QRhi.Feature.ThreeDimensionalTextures` feature is reported as supported at run time.

**Note:** 1D textures are only functional when the :sip:ref:`~PyQt6.QtGui.QRhi.Feature.OneDimensionalTextures` feature is reported as supported at run time. Further, mipmaps on 1D textures are only functional when the :sip:ref:`~PyQt6.QtGui.QRhi.Feature.OneDimensionalTextureMipmaps` feature is reported at run time.
