.. sip:method-description::
    :status: todo
    :pysig: fa7153f7ed1cb6c0fcf2ffb2fac21748
    :realsig: () const
    :digest: 85dd5945596ccbf6ad07b3555a41a674

Returns the size of this image in bytes.

:sip:ref:`~PyQt6.QtCanvasPainter.QCanvasPainter` does not keep copies of the CPU-side :sip:ref:`~PyQt6.QtGui.QImage` data once :sip:ref:`~PyQt6.QtCanvasPainter.QCanvasPainter.addImage` has returned. If the source is a :sip:ref:`~PyQt6.QtCanvasPainter.QCanvasOffscreenCanvas`, then there is no CPU-side image data in the first place. Therefore, the result of this function is an approximation of the GPU memory that is used for the underlying texture.

**Note:** The value is only an estimate based on the image format and dimensions. Qt has no knowledge of how the data for textures is stored and laid out in memory on the GPU side.

**Note:** This function does not take mipmap or multisample data into consideration.
