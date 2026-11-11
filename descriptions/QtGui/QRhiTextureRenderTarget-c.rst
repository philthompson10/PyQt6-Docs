.. sip:class-description::
    :status: todo
    :brief: Texture render target resource
    :digest: 08c32c5c94f1f8b577dac54081aeeb55

Texture render target resource.

A texture render target allows rendering into one or more textures, optionally with a depth texture or depth/stencil renderbuffer.

For multisample rendering the common approach is to use a renderbuffer as the color attachment and set the non-multisample destination texture as the ``resolve texture``. For more information, read the detailed description of the :sip:ref:`~PyQt6.QtGui.QRhiColorAttachment` class.

**Note:** Textures used in combination with :sip:ref:`~PyQt6.QtGui.QRhiTextureRenderTarget` must be created with the :sip:ref:`~PyQt6.QtGui.QRhiTexture.Flag.RenderTarget` flag.

The simplest example of creating a render target with a texture as its single color attachment:

::

    QRhiTexture *texture = rhi->newTexture(QRhiTexture::RGBA8, size, 1, QRhiTexture::RenderTarget);
    texture->create();
    QRhiTextureRenderTarget *rt = rhi->newTextureRenderTarget({ texture });
    rp = rt->newCompatibleRenderPassDescriptor();
    rt->setRenderPassDescriptor(rp);
    rt->create();
    // rt can now be used with beginPass()

**Note:** This is a RHI API with limited compatibility guarantees, see :sip:ref:`~PyQt6.QtGui.QRhi` for details.
