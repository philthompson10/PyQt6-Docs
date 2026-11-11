.. sip:method-description::
    :status: todo
    :pysig: 278ac1de51f6a75bf55b9efb135916c8
    :realsig: (qreal, qreal, qreal, qreal, qreal, QCanvasPainter::PathWinding, QCanvasPainter::PathConnection)
    :digest: 369f9f6cf9e24a5bf457f885a311f530

Creates a new circle arc shaped sub-path. The arc center is at *centerX*, *centerY*, with *radius*, and the arc is drawn from angle *a0* to *a1*, and swept in *direction* (\ :sip:ref:`~PyQt6.QtCanvasPainter.QCanvasPainter.PathWinding.ClockWise` or :sip:ref:`~PyQt6.QtCanvasPainter.QCanvasPainter.PathWinding.CounterClockWise`). When *connection* is :sip:ref:`~PyQt6.QtCanvasPainter.QCanvasPainter.PathConnection.NotConnected`, arc does not add a line from the previous path position to the start of the arc. Angles are specified in radians.

+----------------------------+------------------------------------------+
| |image-qcpainter-arc-webp| | ::                                       |
|                            |                                          |
|                            |     p->beginPath();                      |
|                            |     p->moveTo(100, 100);                 |
|                            |     p->arc(100, 100, 80, 0, 1.5 * M_PI); |
|                            |     p->closePath();                      |
|                            |     p->fill();                           |
|                            |     p->stroke();                         |
+----------------------------+------------------------------------------+

**Note:** While HTML canvas 2D context uses arc() for painting circles, with :sip:ref:`~PyQt6.QtCanvasPainter.QCanvasPainter` it is recommended to use :sip:ref:`~PyQt6.QtCanvasPainter.QCanvasPainter.circle` or :sip:ref:`~PyQt6.QtCanvasPainter.QCanvasPainter.ellipse` for those.

.. |image-qcpainter-arc-webp| image:: ../../../images/qcpainter-arc.webp
