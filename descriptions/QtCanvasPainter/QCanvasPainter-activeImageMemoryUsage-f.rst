.. sip:method-description::
    :status: todo
    :pysig: fa7153f7ed1cb6c0fcf2ffb2fac21748
    :realsig: () const
    :digest: c9a7de5fa1e8f3f4a10a58eb50180d17

Returns an approximation in kilobytes of the memory used by the image (pixel) data for all active :sip:ref:`~PyQt6.QtCanvasPainter.QCanvasImage` instances for this painter that were created by the :sip:ref:`~PyQt6.QtCanvasPainter.QCanvasPainter.addImage` overload taking a :sip:ref:`~PyQt6.QtGui.QImage`. It also includes the data from internally created images for :sip:ref:`~PyQt6.QtCanvasPainter.QCanvasGradient`.

:sip:ref:`~PyQt6.QtCanvasPainter.QCanvasPainter` does not keep copies of the CPU-side :sip:ref:`~PyQt6.QtGui.QImage` data once :sip:ref:`~PyQt6.QtCanvasPainter.QCanvasPainter.addImage` has returned. Therefore, the result of this function is an approximation of the GPU memory that is used for textures.

**Note:** The value is only an estimate based on the image format and dimensions. Qt has no knowledge of how the data for textures is stored and laid out in memory on the GPU side.

Offscreen canvases and externally managed textures registered via the other :sip:ref:`~PyQt6.QtCanvasPainter.QCanvasPainter.addImage` overloads are not taken into account by this function.

For every valid :sip:ref:`~PyQt6.QtCanvasPainter.QCanvasImage`, the individual size in bytes can always be queried by calling :sip:ref:`~PyQt6.QtCanvasPainter.QCanvasImage.sizeInBytes`. That function returns valid results also when the :sip:ref:`~PyQt6.QtCanvasPainter.QCanvasImage` was created from a :sip:ref:`~PyQt6.QtCanvasPainter.QCanvasOffscreenCanvas` or :sip:ref:`~PyQt6.QtGui.QRhiTexture`, but it does not consider mipmap or multisample data.

.. seealso:: :sip:ref:`~PyQt6.QtCanvasPainter.QCanvasPainter.activeImageCount`, :sip:ref:`~PyQt6.QtCanvasPainter.QCanvasPainter.addImage`, :sip:ref:`~PyQt6.QtCanvasPainter.QCanvasPainter.removeImage`.
