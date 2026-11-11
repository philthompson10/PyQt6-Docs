.. sip:method-description::
    :status: todo
    :pysig: 546ade640b6edfbc8a086ef31347e768
    :realsig: (qreal)
    :digest: 7e009c4b387cbcc0f858255f7d0d83a7

Sets the miter limit to *limit*. Miter limit controls when a sharp corner is beveled. When the corner length would become longer than this limit, :sip:ref:`~PyQt6.QtCanvasPainter.QCanvasPainter.LineJoin.Bevel` will be applied between the lines instead. This only has effect with the :sip:ref:`~PyQt6.QtCanvasPainter.QCanvasPainter.LineJoin.Miter` line join. The default limit is ``10.0``.

+-----------------------------------+------------------------------------------------------+
| |image-qcpainter-miterlimit-webp| | ::                                                   |
|                                   |                                                      |
|                                   |     QCanvasPath path;                                |
|                                   |     path.moveTo(20, 40);                             |
|                                   |     path.lineTo(30, 130);                            |
|                                   |     path.lineTo(40, 40);                             |
|                                   |     path.lineTo(55, 80);                             |
|                                   |                                                      |
|                                   |     p->setLineJoin(QCanvasPainter::LineJoin::Miter); |
|                                   |     p->setMiterLimit(20);                            |
|                                   |     p->stroke(path);                                 |
|                                   |                                                      |
|                                   |     p->setMiterLimit(8);                             |
|                                   |     p->translate(65, 0);                             |
|                                   |     p->stroke(path);                                 |
|                                   |                                                      |
|                                   |     p->setMiterLimit(2);                             |
|                                   |     p->translate(65, 0);                             |
|                                   |     p->stroke(path);                                 |
+-----------------------------------+------------------------------------------------------+

.. seealso:: :sip:ref:`~PyQt6.QtCanvasPainter.QCanvasPainter.setLineJoin`.

.. |image-qcpainter-miterlimit-webp| image:: ../../../images/qcpainter-miterlimit.webp
