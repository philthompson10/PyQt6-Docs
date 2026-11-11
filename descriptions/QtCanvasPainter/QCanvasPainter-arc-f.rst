.. sip:method-description::
    :status: todo
    :pysig: acb0c49fc085258b8cae0c94d7787840
    :realsig: (QPointF, qreal, qreal, qreal, QCanvasPainter::PathWinding, QCanvasPainter::PathConnection)
    :digest: 426982bf7a3fdd9f5e2d9fd9f71c6b09

Creates a new circle arc shaped sub-path. The arc center is at *centerPoint*, with *radius*, and the arc is drawn from angle *a0* to *a1*, and swept in *direction* (\ :sip:ref:`~PyQt6.QtCanvasPainter.QCanvasPainter.PathWinding.ClockWise` or :sip:ref:`~PyQt6.QtCanvasPainter.QCanvasPainter.PathWinding.CounterClockWise`). When *connection* is :sip:ref:`~PyQt6.QtCanvasPainter.QCanvasPainter.PathConnection.NotConnected`, arc does not add a line from the previous path position to the start of the arc. Angles are specified in radians.

**Note:** While HTML canvas 2D context uses :sip:ref:`~PyQt6.QtCanvasPainter.QCanvasPainter.arc` for painting circles, with :sip:ref:`~PyQt6.QtCanvasPainter.QCanvasPainter` it is recommended to use :sip:ref:`~PyQt6.QtCanvasPainter.QCanvasPainter.circle` or :sip:ref:`~PyQt6.QtCanvasPainter.QCanvasPainter.ellipse` for those.
