.. sip:method-description::
    :status: todo
    :pysig: 18fc5c924ded5804300a9bbe6932ebba
    :realsig: (QCanvasPainter*)
    :digest: 20d5cb3e7cad8c539fe9ac2d76f7ec9c

This function is called at the start of rendering using *painter*, before :sip:ref:`~PyQt6.QtCanvasPainter.QCanvasPainterItemRenderer.paint`.

There is no render target active when this function is invoked. Call :sip:ref:`~PyQt6.QtCanvasPainter.QCanvasPainterItemRenderer.beginCanvasPainting` to initialize drawing into an offscreen canvas.

.. seealso:: :sip:ref:`~PyQt6.QtCanvasPainter.QCanvasPainterItemRenderer.beginCanvasPainting`, :sip:ref:`~PyQt6.QtCanvasPainter.QCanvasPainterItemRenderer.endCanvasPainting`.
