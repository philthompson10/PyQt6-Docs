.. sip:method-description::
    :status: todo
    :pysig: b2bdfe6a960658bbf499a571ee1d24b8
    :realsig: (QSize, int, QCanvasOffscreenCanvas::Flags)
    :digest: a7514d47266a17dfead4a2349f723238

Returns a new offscreen canvas with the given *pixelSize*, *sampleCount*, and *flags*.

The size of the canvas is specified in pixels. The *pixelSize*, *sampleCount*, and *flags* properties are immutable afterwards. To get a canvas with a different size, sample count, or flags, create a new one.

To target an offscreen canvas with with draw commands, call the appropriate QCanvasRhiPaintDriver::beginPaint() overload when working with the lower level API, or :sip:ref:`~PyQt6.QtCanvasPainter.QCanvasPainterWidget.beginCanvasPainting` or :sip:ref:`~PyQt6.QtCanvasPainter.QCanvasPainterItemRenderer.beginCanvasPainting` when using the convenience widget or Qt Quick item classes.

Normally the contents of the canvas is cleared when painting to it. To disable this, pass :sip:ref:`~PyQt6.QtCanvasPainter.QCanvasOffscreenCanvas.Flag.PreserveContents` in *flags*.

To request multisample rendering onto the canvas (multisample antialiasing, MSAA), set a sample count larger than 1, such as 4 or 8. Preserving the canvas contents between render passes is not supported however when multisampling is enabled, and the :sip:ref:`~PyQt6.QtCanvasPainter.QCanvasOffscreenCanvas.Flag.PreserveContents` flag will not work in this case.

**Note:** An offscreen canvas is backed by a texture independent from the main render target, and rendering to it always happens with a scale factor (device pixel ratio) of 1. For example, to create a canvas matching the true rendering dimensions of a :sip:ref:`~PyQt6.QtCanvasPainter.QCanvasPainterWidget`, pass ``size() \* devicePixelRatio()`` as *pixelSize*, because the ``size()`` of the widget is just the logical size without the scale factor included.
