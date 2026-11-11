.. sip:class-description::
    :status: todo
    :brief: Describes a texture upload operation
    :digest: ea1187f2d1596e32fe003317bd6c7922

Describes a texture upload operation.

Used with :sip:ref:`~PyQt6.QtGui.QRhiResourceUpdateBatch.uploadTexture`. That function has two variants: one taking a :sip:ref:`~PyQt6.QtGui.QImage` and one taking a :sip:ref:`~PyQt6.QtGui.QRhiTextureUploadDescription`. The former is a convenience version, internally creating a :sip:ref:`~PyQt6.QtGui.QRhiTextureUploadDescription` with a single image targeting level 0 for layer 0.

An example of the common, simple case of wanting to upload the contents of a :sip:ref:`~PyQt6.QtGui.QImage` to a :sip:ref:`~PyQt6.QtGui.QRhiTexture` with a matching pixel size:

::

    QImage image(256, 256, QImage::Format_RGBA8888);
    image.fill(Qt::green); // or could use a QPainter targeting image
    QRhiTexture *texture = rhi->newTexture(QRhiTexture::RGBA8, QSize(256, 256));
    texture->create();
    QRhiResourceUpdateBatch *u = rhi->nextResourceUpdateBatch();
    u->uploadTexture(texture, image);

When cubemaps, pre-generated mip images, compressed textures, or partial uploads are involved, applications will have to use this class instead.

:sip:ref:`~PyQt6.QtGui.QRhiTextureUploadDescription` also enables specifying batched uploads, which are useful for example when generating an atlas or glyph cache texture: multiple, partial uploads for the same subresource (meaning the same layer and level) are supported, and can be, depending on the backend and the underlying graphics API, more efficient when batched into the same :sip:ref:`~PyQt6.QtGui.QRhiTextureUploadDescription` as opposed to issuing individual :sip:ref:`~PyQt6.QtGui.QRhiResourceUpdateBatch.uploadTexture` commands for each of them.

**Note:** Cubemaps have one layer for each of the six faces in the order +X, -X, +Y, -Y, +Z, -Z.

For example, specifying the faces of a cubemap could look like the following:

::

    QImage faces[6];
    // ...
    QVarLengthArray<QRhiTextureUploadEntry, 6> entries;
    for (int i = 0; i < 6; ++i)
      entries.append(QRhiTextureUploadEntry(i, 0, faces[i]));
    QRhiTextureUploadDescription desc;
    desc.setEntries(entries.cbegin(), entries.cend());
    resourceUpdates->uploadTexture(texture, desc);

Another example that specifies mip images for a compressed texture:

::

    QList<QRhiTextureUploadEntry> entries;
    const int mipCount = rhi->mipLevelsForSize(compressedTexture->pixelSize());
    for (int level = 0; level < mipCount; ++level) {
        const QByteArray compressedDataForLevel = ..
        entries.append(QRhiTextureUploadEntry(0, level, compressedDataForLevel));
    }
    QRhiTextureUploadDescription desc;
    desc.setEntries(entries.cbegin(), entries.cend());
    resourceUpdates->uploadTexture(compressedTexture, desc);

With partial uploads targeting the same subresource, it is recommended to batch them into a single upload request, whenever possible:

::

    QRhiTextureSubresourceUploadDescription subresDesc(image);
    subresDesc.setSourceSize(QSize(10, 10));
    subResDesc.setDestinationTopLeft(QPoint(50, 40));
    QRhiTextureUploadEntry entry(0, 0, subresDesc); // layer 0, level 0

    QRhiTextureSubresourceUploadDescription subresDesc2(image);
    subresDesc2.setSourceSize(QSize(30, 40));
    subResDesc2.setDestinationTopLeft(QPoint(100, 200));
    QRhiTextureUploadEntry entry2(0, 0, subresDesc2); // layer 0, level 0, i.e. same subresource

    QRhiTextureUploadDescription desc({ entry, entry2});
    resourceUpdates->uploadTexture(texture, desc);

**Note:** This is a RHI API with limited compatibility guarantees, see :sip:ref:`~PyQt6.QtGui.QRhi` for details.

.. seealso:: :sip:ref:`~PyQt6.QtGui.QRhiResourceUpdateBatch`.
