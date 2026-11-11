.. sip:method-description::
    :status: todo
    :pysig: 29b4696bca64b02b0c291bc26b783ac9
    :realsig: (QRhiTexture*, QRhiTexture*, const QRhiTextureCopyDescription&)
    :digest: c357cdc09db9ecd31a1e6b3e9e615b98

Enqueues a texture-to-texture copy operation from *src* into *dst* as described by *desc*.

**Note:** The source texture *src* must be created with :sip:ref:`~PyQt6.QtGui.QRhiTexture.Flag.UsedAsTransferSource`.

**Note:** The format of the textures must match. With most graphics APIs the data is copied as-is without any format conversions. If *dst* and *src* are created with different formats, unspecified issues may arise.
