.. sip:method-description::
    :status: todo
    :pysig: 88a7de119eeb40b0aa1f27be0715c1b4
    :realsig: (const QRhiReadbackDescription&, QRhiReadbackResult*)
    :digest: fd54d8ed78ec3e08c4d77a53acea104a

Enqueues a texture-to-host copy operation as described by *rb*.

Normally *rb* will specify a :sip:ref:`~PyQt6.QtGui.QRhiTexture` as the source. However, when the swapchain in the current frame was created with :sip:ref:`~PyQt6.QtGui.QRhiSwapChain.Flag.UsedAsTransferSource`, it can also be the source of the readback. For this, leave the texture set to null in *rb*.

Unlike other operations, the results here need to be processed by the application. Therefore, *result* provides not just the data but also a callback as operations on the batch are asynchronous by nature:

::

    rhi->beginFrame(swapchain);
    cb->beginPass(swapchain->currentFrameRenderTarget(), colorClear, dsClear);
    // ...
    QRhiReadbackResult *rbResult = new QRhiReadbackResult;
    rbResult->completed = [rbResult] {
        {
            const QImage::Format fmt = QImage::Format_RGBA8888_Premultiplied; // fits QRhiTexture::RGBA8
            const uchar *p = reinterpret_cast<const uchar *>(rbResult->data.constData());
            QImage image(p, rbResult->pixelSize.width(), rbResult->pixelSize.height(), fmt);
            image.save("result.png");
        }
        delete rbResult;
    };
    QRhiResourceUpdateBatch *u = nextResourceUpdateBatch();
    QRhiReadbackDescription rb; // no texture -> uses the current backbuffer of sc
    u->readBackTexture(rb, rbResult);
    cb->endPass(u);
    rhi->endFrame(swapchain);

**Note:** The texture must be created with :sip:ref:`~PyQt6.QtGui.QRhiTexture.Flag.UsedAsTransferSource`.

**Note:** Multisample textures cannot be read back.

**Note:** The readback returns raw byte data, in order to allow the applications to interpret it in any way they see fit. Be aware of the blending settings of rendering code: if the blending is set up to rely on premultiplied alpha, the results of the readback must also be interpreted as Premultiplied.

**Note:** When interpreting the resulting raw data, be aware that the readback happens with a byte ordered format. A :sip:ref:`~PyQt6.QtGui.QRhiTexture.Format.RGBA8` texture maps therefore to byte ordered :sip:ref:`~PyQt6.QtGui.QImage` formats, such as, :sip:ref:`~PyQt6.QtGui.QImage.Format.Format_RGBA8888`.

**Note:** The asynchronous readback is guaranteed to have completed when one of the following conditions is met: :sip:ref:`~PyQt6.QtGui.QRhi.finish` has been called; or, at least ``N`` frames have been :sip:ref:`~PyQt6.QtGui.QRhi.endFrame`, including the frame that issued the readback operation, and the :sip:ref:`~PyQt6.QtGui.QRhi.beginFrame` has been started, where ``N`` is the :sip:ref:`~PyQt6.QtGui.QRhi.resourceLimit` returned for :sip:ref:`~PyQt6.QtGui.QRhi.ResourceLimit.MaxAsyncReadbackFrames`.

A single readback operation copies one mip level of one layer (cubemap face or 3D slice or texture array element) at a time. The level and layer are specified by the respective fields in *rb*.

.. seealso:: :sip:ref:`~PyQt6.QtGui.QRhiResourceUpdateBatch.readBackBuffer`, :sip:ref:`~PyQt6.QtGui.QRhi.resourceLimit`.
