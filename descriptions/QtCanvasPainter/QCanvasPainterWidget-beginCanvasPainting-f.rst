.. sip:method-description::
    :status: todo
    :pysig: dd5e73b1d4a76ce0a0dfb868f41bd317
    :realsig: (QCanvasOffscreenCanvas&)
    :digest: c7dee9c3d12d96c2ccb5482ec46df163

Starts recording :sip:ref:`~PyQt6.QtCanvasPainter.QCanvasPainter` draw commands targeting *canvas*.

**Note:** This function should only be called from :sip:ref:`~PyQt6.QtCanvasPainter.QCanvasPainterWidget.prePaint`.

beginCanvasPainting() must always be followed by corresponding :sip:ref:`~PyQt6.QtCanvasPainter.QCanvasPainterWidget.endCanvasPainting` before returning from :sip:ref:`~PyQt6.QtCanvasPainter.QCanvasPainterWidget.prePaint`.

The following snippet from a :sip:ref:`~PyQt6.QtCanvasPainter.QCanvasPainterWidget` subclass shows how an offscreen canvas could be rendered into and then used as an image or image pattern when drawing the contents for the widget:

.. literalinclude:: ../../../snippets/qtcanvaspainter-src-canvaspainter-doc-snippets-widget-canvas-ex-1.py
