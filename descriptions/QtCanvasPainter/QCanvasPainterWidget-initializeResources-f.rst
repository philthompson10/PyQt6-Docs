.. sip:method-description::
    :status: todo
    :pysig: 18fc5c924ded5804300a9bbe6932ebba
    :realsig: (QCanvasPainter*)
    :digest: ab1da6da75258a5301d39106c1251663

Reimplement this method to initialize resources using *painter*. Generally, this will be called once before the first :sip:ref:`~PyQt6.QtCanvasPainter.QCanvasPainterWidget.prePaint` and :sip:ref:`~PyQt6.QtCanvasPainter.QCanvasPainterWidget.paint`. An exception is when graphics resources are lost, see :sip:ref:`~PyQt6.QtCanvasPainter.QCanvasPainterWidget.graphicsResourcesInvalidated`. In that case, this method will get invoked again afterwards.

The default implementation is empty.
