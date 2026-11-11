.. sip:class-description::
    :status: todo
    :brief: Describes the source for one mip level in a layer in a texture upload operation
    :digest: bec22a223756c19c29a67dfbb0475176

Describes the source for one mip level in a layer in a texture upload operation.

The source content is specified either as a :sip:ref:`~PyQt6.QtGui.QImage` or as a raw blob. The former is only allowed for uncompressed textures with a format that can be mapped to :sip:ref:`~PyQt6.QtGui.QImage`, while the latter is supported for all formats, including floating point and compressed.

**Note:** image() and data() cannot be both set at the same time.

destinationTopLeft() specifies the top-left corner of the target rectangle. Defaults to (0, 0).

An empty sourceSize() (the default) indicates that size is assumed to be the size of the subresource. With :sip:ref:`~PyQt6.QtGui.QImage`-based uploads this implies that the size of the source image() must match the subresource. When providing raw data instead, sufficient number of bytes must be provided in data().

sourceTopLeft() is supported only for :sip:ref:`~PyQt6.QtGui.QImage`-based uploads, and specifies the top-left corner of the source rectangle.

**Note:** Setting sourceSize() or sourceTopLeft() may trigger a :sip:ref:`~PyQt6.QtGui.QImage` copy internally, depending on the format and the backend.

When providing raw data, and the stride is not specified via setDataStride(), the stride (row pitch, row length in bytes) of the provided data must be equal to ``width \* pixelSize`` where ``pixelSize`` is the number of bytes used for one pixel, and there must be no additional padding between rows. There is no row start alignment requirement.

When there is unused data at the end of each row in the input raw data, call setDataStride() with the total number of bytes per row. The stride must always be a multiple of the number of bytes for one pixel. The row stride is only applicable to image data for textures with an uncompressed format.

**Note:** The format of the source data must be compatible with the texture format. With many graphics APIs the data is copied as-is into a staging buffer, there is no intermediate format conversion provided by :sip:ref:`~PyQt6.QtGui.QRhi`. This applies to floating point formats as well, with, for example, RGBA16F requiring half floats in the source data.

**Note:** Setting the stride via setDataStride() is only functional when :sip:ref:`~PyQt6.QtGui.QRhi.Feature.ImageDataStride` is reported as :sip:ref:`~PyQt6.QtGui.QRhi.isFeatureSupported`. In practice this can be expected to be supported everywhere except for OpenGL ES 2.0.

**Note:** When a :sip:ref:`~PyQt6.QtGui.QImage` is given, the stride returned from QImage::bytesPerLine() is taken into account automatically.

**Warning:** When a :sip:ref:`~PyQt6.QtGui.QImage` is given and the :sip:ref:`~PyQt6.QtGui.QImage` does not own the underlying pixel data, it is up to the caller to ensure that the associated data stays valid until the end of the frame. (just submitting the resource update batch is not sufficient, the data must stay valid until :sip:ref:`~PyQt6.QtGui.QRhi.endFrame` is called in order to be portable across all backends) If this cannot be ensured, the caller is strongly encouraged to call QImage::detach() on the image before passing it to uploadTexture().

**Note:** This is a RHI API with limited compatibility guarantees, see :sip:ref:`~PyQt6.QtGui.QRhi` for details.

.. seealso:: :sip:ref:`~PyQt6.QtGui.QRhiTextureUploadDescription`.
