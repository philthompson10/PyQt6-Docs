.. sip:method-description::
    :status: todo
    :pysig: fa7153f7ed1cb6c0fcf2ffb2fac21748
    :realsig: () const
    :digest: 4a54e85ac151be7f537bb45e1d33e074

Returns the number of active :sip:ref:`~PyQt6.QtCanvasPainter.QCanvasImage` objects registered with this :sip:ref:`~PyQt6.QtCanvasPainter.QCanvasPainter`. This also includes the internally created images for :sip:ref:`~PyQt6.QtCanvasPainter.QCanvasGradient`.

:sip:ref:`~PyQt6.QtCanvasPainter.QCanvasImage` objects created by registering :sip:ref:`~PyQt6.QtCanvasPainter.QCanvasOffscreenCanvas` instances or externally managed textures are not taken into account by this function.

.. seealso:: :sip:ref:`~PyQt6.QtCanvasPainter.QCanvasPainter.activeImageMemoryUsage`, :sip:ref:`~PyQt6.QtCanvasPainter.QCanvasPainter.addImage`, :sip:ref:`~PyQt6.QtCanvasPainter.QCanvasPainter.removeImage`.
