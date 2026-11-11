.. sip:method-description::
    :status: todo
    :pysig: 43b53cebe601f188143f3aa843779358
    :realsig: (QRhiRenderBuffer::Type, const QSize&, int, QRhiRenderBuffer::Flags, QRhiTexture::Format)
    :digest: 7b313339d7643c9515bc795c9f524d3e

Returns a new renderbuffer with the specified *type*, *pixelSize*, *sampleCount*, and *flags*.

When *backingFormatHint* is set to a texture format other than :sip:ref:`~PyQt6.QtGui.QRhiTexture.Format.UnknownFormat`, it may be used by the backend to decide what format to use for the storage backing the renderbuffer.

**Note:** *backingFormatHint* becomes relevant typically when multisampling and floating point texture formats are involved: rendering into a multisample :sip:ref:`~PyQt6.QtGui.QRhiRenderBuffer` and then resolving into a non-RGBA8 :sip:ref:`~PyQt6.QtGui.QRhiTexture` implies (with some graphics APIs) that the storage backing the :sip:ref:`~PyQt6.QtGui.QRhiRenderBuffer` uses the matching non-RGBA8 format. That means that passing a format like :sip:ref:`~PyQt6.QtGui.QRhiTexture.Format.RGBA32F` is important, because backends will typically opt for :sip:ref:`~PyQt6.QtGui.QRhiTexture.Format.RGBA8` by default, which would then break later on due to attempting to set up RGBA8->RGBA32F multisample resolve in the color attachment(s) of the :sip:ref:`~PyQt6.QtGui.QRhiTextureRenderTarget`.

.. seealso:: :sip:ref:`~PyQt6.QtGui.QRhiResource.destroy`.
