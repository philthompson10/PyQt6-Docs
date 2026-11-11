.. sip:class-description::
    :status: todo
    :brief: Texture resource
    :digest: 7617ffd871b96b470d8256e35c06c715

Texture resource.

A :sip:ref:`~PyQt6.QtGui.QRhiTexture` encapsulates a native texture object, such as a ``VkImage`` or ``MTLTexture``.

A :sip:ref:`~PyQt6.QtGui.QRhiTexture` instance is always created by calling :sip:ref:`~PyQt6.QtGui.QRhi.newTexture`. This creates no native graphics resources. To do that, call create() after setting the appropriate options, such as the format and size, although in most cases these are already set based on the arguments passed to :sip:ref:`~PyQt6.QtGui.QRhi.newTexture`.

Setting the flags correctly is essential, otherwise various errors can occur depending on the underlying :sip:ref:`~PyQt6.QtGui.QRhi` backend and graphics API. For example, when a texture will be rendered into from a render pass via :sip:ref:`~PyQt6.QtGui.QRhiTextureRenderTarget`, the texture must be created with the :sip:ref:`~PyQt6.QtGui.QRhiTexture.Flag.RenderTarget` flag set. Similarly, when the texture is going to be :sip:ref:`~PyQt6.QtGui.QRhiResourceUpdateBatch.readBackTexture`, the :sip:ref:`~PyQt6.QtGui.QRhiTexture.Flag.UsedAsTransferSource` flag must be set upfront. Mipmapped textures must have the :sip:ref:`~PyQt6.QtGui.QRhiTexture.Flag.MipMapped` flag set. And so on. It is not possible to change the flags once create() has succeeded. To release the existing and create a new native texture object with the changed settings, call the setters and call create() again. This then might be a potentially expensive operation.

.. _qrhitexture-example-usage:

Example usage
.............

To create a 2D texture with a size of 512x512 pixels and set its contents to all green:

::

    QRhiTexture *texture = rhi->newTexture(QRhiTexture::RGBA8, QSize(512, 512));
    if (!texture->create()) { error(); }
    QRhiResourceUpdateBatch *batch = rhi->nextResourceUpdateBatch();
    QImage image(512, 512, QImage::Format_RGBA8888);
    image.fill(Qt::green);
    batch->uploadTexture(texture, image);
    // ...
    commandBuffer->resourceUpdate(batch); // or, alternatively, pass 'batch' to a beginPass() call

.. _qrhitexture-common-patterns:

Common patterns
...............

A call to create() destroys any existing native resources if create() was successfully called before. If those native resources are still in use by an in-flight frame (i.e., there's a chance they are still read by the GPU), the destroying of those resources is deferred automatically. Thus a very common and convenient pattern to safely change the size of an already existing texture is the following. In practice this drops and creates a whole new native texture resource underneath, so it is not necessarily a cheap operation, but is more convenient and still faster than the alternatives, because by not destroying the ``texture`` object itself, all references to it stay valid in other data structures (e.g., in any QShaderResourceBinding the :sip:ref:`~PyQt6.QtGui.QRhiTexture` is referenced from).

::

    // determine newSize, e.g. based on the swapchain's output size or other factors
    if (texture->pixelSize() != newSize) {
        texture->setPixelSize(newSize);
        if (!texture->create()) { error(); }
    }
    // continue using texture, fill it with new data

**Note:** This is a RHI API with limited compatibility guarantees, see :sip:ref:`~PyQt6.QtGui.QRhi` for details.

.. seealso:: :sip:ref:`~PyQt6.QtGui.QRhiResourceUpdateBatch`, :sip:ref:`~PyQt6.QtGui.QRhi`, :sip:ref:`~PyQt6.QtGui.QRhiTextureRenderTarget`.
