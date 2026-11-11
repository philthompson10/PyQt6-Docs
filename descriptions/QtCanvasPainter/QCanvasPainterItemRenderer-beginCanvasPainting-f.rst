.. sip:method-description::
    :status: todo
    :pysig: dd5e73b1d4a76ce0a0dfb868f41bd317
    :realsig: (QCanvasOffscreenCanvas&)
    :digest: a3b7396c1027bc211e991cd431382998

Starts recording :sip:ref:`~PyQt6.QtCanvasPainter.QCanvasPainter` draw commands targeting *canvas*.

**Note:** This function should only be called from :sip:ref:`~PyQt6.QtCanvasPainter.QCanvasPainterItemRenderer.prePaint`.

beginCanvasPainting() must always be followed by corresponding :sip:ref:`~PyQt6.QtCanvasPainter.QCanvasPainterItemRenderer.endCanvasPainting` before returning from :sip:ref:`~PyQt6.QtCanvasPainter.QCanvasPainterItemRenderer.prePaint`.
