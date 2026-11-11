.. sip:class-description::
    :status: todo
    :brief: Describes the color and depth or depth/stencil attachments of a render target
    :digest: bfc31cb2f1208f627ef64609c9ca2e30

Describes the color and depth or depth/stencil attachments of a render target.

A texture render target has zero or more textures as color attachments, zero or one renderbuffer as combined depth/stencil buffer or zero or one texture as depth buffer.

**Note:** depthStencilBuffer() and depthTexture() cannot be both set (cannot be non-null at the same time).

Let's look at some example usages in combination with :sip:ref:`~PyQt6.QtGui.QRhiTextureRenderTarget`.

Due to the constructors, the targeting a texture (and no depth/stencil buffer) is simple:

::

    QRhiTexture *texture = rhi->newTexture(QRhiTexture::RGBA8, QSize(256, 256), 1, QRhiTexture::RenderTarget);
    texture->create();
    QRhiTextureRenderTarget *rt = rhi->newTextureRenderTarget({ texture }));

The following creates a texture render target that is set up to target mip level #2 of a texture:

::

    QRhiTexture *texture = rhi->newTexture(QRhiTexture::RGBA8, QSize(512, 512), 1, QRhiTexture::RenderTarget | QRhiTexture::MipMapped);
    texture->create();
    QRhiColorAttachment colorAtt(texture);
    colorAtt.setLevel(2);
    QRhiTextureRenderTarget *rt = rhi->newTextureRenderTarget({ colorAtt });

Another example, this time to render into a depth texture:

::

    QRhiTexture *shadowMap = rhi->newTexture(QRhiTexture::D32F, QSize(1024, 1024), 1, QRhiTexture::RenderTarget);
    shadowMap->create();
    QRhiTextureRenderTargetDescription rtDesc;
    rtDesc.setDepthTexture(shadowMap);
    QRhiTextureRenderTarget *rt = rhi->newTextureRenderTarget(rtDesc);

A very common case, having a texture as the color attachment and a renderbuffer as depth/stencil to enable depth testing:

::

    QRhiTexture *texture = rhi->newTexture(QRhiTexture::RGBA8, QSize(512, 512), 1, QRhiTexture::RenderTarget);
    texture->create();
    QRhiRenderBuffer *depthStencil = rhi->newRenderBuffer(QRhiRenderBuffer::DepthStencil, QSize(512, 512));
    depthStencil->create();
    QRhiTextureRenderTargetDescription rtDesc({ texture }, depthStencil);
    QRhiTextureRenderTarget *rt = rhi->newTextureRenderTarget(rtDesc);

Finally, to enable multisample rendering in a portable manner (so also supporting OpenGL ES 3.0), using a :sip:ref:`~PyQt6.QtGui.QRhiRenderBuffer` as the (multisample) color buffer and then resolving into a regular (non-multisample) 2D texture. To enable depth testing, a depth-stencil buffer, which also must use the same sample count, is used as well:

::

    QRhiRenderBuffer *colorBuffer = rhi->newRenderBuffer(QRhiRenderBuffer::Color, QSize(512, 512), 4); // 4x MSAA
    colorBuffer->create();
    QRhiRenderBuffer *depthStencil = rhi->newRenderBuffer(QRhiRenderBuffer::DepthStencil, QSize(512, 512), 4);
    depthStencil->create();
    QRhiTexture *texture = rhi->newTexture(QRhiTexture::RGBA8, QSize(512, 512), 1, QRhiTexture::RenderTarget);
    texture->create();
    QRhiColorAttachment colorAtt(colorBuffer);
    colorAtt.setResolveTexture(texture);
    QRhiTextureRenderTarget *rt = rhi->newTextureRenderTarget({ colorAtt, depthStencil });

**Note:** when multisample resolving is enabled, the multisample data may not be written out at all. This means that the multisample texture in a color attachment must not be used afterwards with shaders for sampling (or other purposes) whenever a resolve texture is set, since the multisample color buffer is merely an intermediate storage then that gets no data written back on some GPU architectures at all. See :sip:ref:`~PyQt6.QtGui.QRhiTextureRenderTarget.Flag` for more details.

**Note:** When using setDepthTexture(), not setDepthStencilBuffer(), and the depth (stencil) data is not of interest afterwards, set the DoNotStoreDepthStencilContents flag on the :sip:ref:`~PyQt6.QtGui.QRhiTextureRenderTarget`. This allows indicating to the underlying 3D API that the depth/stencil data can be discarded, leading potentially to better performance with tiled GPU architectures. When the depth-stencil buffer is a :sip:ref:`~PyQt6.QtGui.QRhiRenderBuffer` (and also for the multisample color texture, see previous note) this is implicit, but with a depth (stencil) :sip:ref:`~PyQt6.QtGui.QRhiTexture` the intention needs to be declared explicitly. By default :sip:ref:`~PyQt6.QtGui.QRhi` assumes that the data is of interest (e.g., the depth texture is sampled in a shader afterwards).

**Note:** This is a RHI API with limited compatibility guarantees, see :sip:ref:`~PyQt6.QtGui.QRhi` for details.

.. seealso:: :sip:ref:`~PyQt6.QtGui.QRhiColorAttachment`, :sip:ref:`~PyQt6.QtGui.QRhiTextureRenderTarget`.
