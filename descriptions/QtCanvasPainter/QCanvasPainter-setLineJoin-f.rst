.. sip:method-description::
    :status: todo
    :pysig: 3e20a28fed7e8712a931a59c1449b3ef
    :realsig: (QCanvasPainter::LineJoin)
    :digest: 1c2c2ec2970f3fc36c263aaa243a47b6

Sets the line join of strokes to *join*. The default line join is ``QCanvasPainter::LineJoin::Miter``.

+---------------------------------+------------------------------------------------------+
| |image-qcpainter-linejoin-webp| | ::                                                   |
|                                 |                                                      |
|                                 |     QCanvasPath path;                                |
|                                 |     path.moveTo(40, 20);                             |
|                                 |     path.lineTo(100, 80);                            |
|                                 |     path.lineTo(160, 40);                            |
|                                 |     path.lineTo(160, 70);                            |
|                                 |     p->setLineJoin(QCanvasPainter::LineJoin::Miter); |
|                                 |     p->stroke(path, -1);                             |
|                                 |     p->setLineJoin(QCanvasPainter::LineJoin::Bevel); |
|                                 |     p->translate(0, 50);                             |
|                                 |     p->stroke(path, -1);                             |
|                                 |     p->setLineJoin(QCanvasPainter::LineJoin::Round); |
|                                 |     p->translate(0, 50);                             |
|                                 |     p->stroke(path, -1);                             |
+---------------------------------+------------------------------------------------------+

.. seealso:: :sip:ref:`~PyQt6.QtCanvasPainter.QCanvasPainter.setMiterLimit`.

.. |image-qcpainter-linejoin-webp| image:: ../../../images/qcpainter-linejoin.webp
