.. sip:class-description::
    :status: todo
    :brief: Specifies a viewport rectangle
    :digest: 67c432f00f4c4b69fa81dbd232edb85d

Specifies a viewport rectangle.

Used with :sip:ref:`~PyQt6.QtGui.QRhiCommandBuffer.setViewport`.

:sip:ref:`~PyQt6.QtGui.QRhi` assumes OpenGL-style viewport coordinates, meaning x and y are bottom-left. Negative width or height are not allowed.

Typical usage is like the following:

::

    const QSize outputSizeInPixels = swapchain->currentPixelSize();
    const QRhiViewport viewport(0, 0, outputSizeInPixels.width(), outputSizeInPixels.height());
    cb->beginPass(swapchain->currentFrameRenderTarget(), Qt::black, { 1.0f, 0 });
    cb->setGraphicsPipeline(ps);
    cb->setViewport(viewport);
    // ...

**Note:** This is a RHI API with limited compatibility guarantees, see :sip:ref:`~PyQt6.QtGui.QRhi` for details.

.. seealso:: :sip:ref:`~PyQt6.QtGui.QRhiCommandBuffer.setViewport`, :sip:ref:`~PyQt6.QtGui.QRhi.clipSpaceCorrMatrix`, :sip:ref:`~PyQt6.QtGui.QRhiScissor`.
