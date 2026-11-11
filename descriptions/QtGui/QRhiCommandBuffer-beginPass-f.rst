.. sip:method-description::
    :status: todo
    :pysig: 6ceef16adeec3a289b48d1e2825ea220
    :realsig: (QRhiRenderTarget*, const QColor&, const QRhiDepthStencilClearValue&, QRhiResourceUpdateBatch*, QRhiCommandBuffer::BeginPassFlags)
    :digest: 4bb4cc7d24755b8f4d5ae05bd15c1f0d

Records starting a new render pass targeting the render target *rt*.

*resourceUpdates*, when not null, specifies a resource update batch that is to be committed and then released.

The color and depth/stencil buffers of the render target are normally cleared. The clear values are specified in *colorClearValue* and *depthStencilClearValue*. The exception is when the render target was created with :sip:ref:`~PyQt6.QtGui.QRhiTextureRenderTarget.Flag.PreserveColorContents` and/or :sip:ref:`~PyQt6.QtGui.QRhiTextureRenderTarget.Flag.PreserveDepthStencilContents`. The clear values are ignored then.

**Note:** Enabling preserved color or depth contents leads to decreased performance depending on the underlying hardware. Mobile GPUs with tiled architecture benefit from not having to reload the previous contents into the tile buffer. Similarly, a :sip:ref:`~PyQt6.QtGui.QRhiTextureRenderTarget` with a :sip:ref:`~PyQt6.QtGui.QRhiTexture` as the depth buffer is less efficient than a :sip:ref:`~PyQt6.QtGui.QRhiRenderBuffer` since using a depth texture triggers requiring writing the data out to it, while with renderbuffers this is not needed (as the API does not allow sampling or reading from a renderbuffer).

**Note:** Do not assume that any state or resource bindings persist between passes.

**Note:** The :sip:ref:`~PyQt6.QtGui.QRhiCommandBuffer`'s ``set`` and ``draw`` functions can only be called inside a pass. Also, with the exception of :sip:ref:`~PyQt6.QtGui.QRhiCommandBuffer.setGraphicsPipeline`, they expect to have a pipeline set already on the command buffer. Unspecified issues may arise otherwise, depending on the backend.

If *rt* is a :sip:ref:`~PyQt6.QtGui.QRhiTextureRenderTarget`, beginPass() performs a check to see if the texture and renderbuffer objects referenced from the render target are up-to-date. This is similar to what :sip:ref:`~PyQt6.QtGui.QRhiCommandBuffer.setShaderResources` does for :sip:ref:`~PyQt6.QtGui.QRhiShaderResourceBindings`. If any of the attachments had been rebuilt since QRhiTextureRenderTarget::create(), an implicit call to create() is made on *rt*. Therefore, if *rt* has a :sip:ref:`~PyQt6.QtGui.QRhiTexture` color attachment ``texture``, and one needs to make the texture a different size, the following is then valid:

::

    QRhiTextureRenderTarget *rt = rhi->newTextureRenderTarget({ { texture } });
    rt->create();
    // ...
    texture->setPixelSize(new_size);
    texture->create();
    cb->beginPass(rt, colorClear, dsClear); // this is ok, no explicit rt->create() is required before

*flags* allow controlling certain advanced functionality. One commonly used flag is ``ExternalContents``. This should be specified whenever :sip:ref:`~PyQt6.QtGui.QRhiCommandBuffer.beginExternal` will be called within the pass started by this function.

.. seealso:: :sip:ref:`~PyQt6.QtGui.QRhiCommandBuffer.endPass`, BeginPassFlags.
