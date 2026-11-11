.. sip:method-description::
    :status: todo
    :pysig: 25e196d4d221d4ff488d81b2f6445ca4
    :realsig: (QCanvasPainter::LineCap)
    :digest: 150b734b067c0b851b7208fab6fed617

Sets the end of the line for strokes to *cap*. The default line cap is ``QCanvasPainter::LineCap::Butt``.

+--------------------------------+-----------------------------------------------------+
| |image-qcpainter-linecap-webp| | ::                                                  |
|                                |                                                     |
|                                |     QCanvasPath path;                               |
|                                |     path.moveTo(40, 60);                            |
|                                |     path.lineTo(160, 60);                           |
|                                |     p->setLineCap(QCanvasPainter::LineCap::Butt);   |
|                                |     p->stroke(path, -1);                            |
|                                |     p->setLineCap(QCanvasPainter::LineCap::Square); |
|                                |     p->translate(0, 40);                            |
|                                |     p->stroke(path, -1);                            |
|                                |     p->setLineCap(QCanvasPainter::LineCap::Round);  |
|                                |     p->translate(0, 40);                            |
|                                |     p->stroke(path, -1);                            |
+--------------------------------+-----------------------------------------------------+

.. |image-qcpainter-linecap-webp| image:: ../../../images/qcpainter-linecap.webp
