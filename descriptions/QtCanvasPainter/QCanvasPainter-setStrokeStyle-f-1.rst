.. sip:method-description::
    :status: todo
    :pysig: 90a04f1cd47e7fe2fc8019d75e1a1a27
    :realsig: (const QCanvasBrush&)
    :digest: 3799721d5fae6d007f79d4a75297fb6c

Sets the stroke style to *brush*. The default stroke style is solid black (0, 0, 0, 1).

+-------------------------------------+-------------------------------------------------+
| |image-qcpainter-strokestyle2-webp| | ::                                              |
|                                     |                                                 |
|                                     |     QCanvasLinearGradient g1(180, 20, 20, 180); |
|                                     |     g1.setStartColor(QColor(44, 222, 133));     |
|                                     |     g1.setEndColor(Qt::black);                  |
|                                     |     p->setStrokeStyle(g1);                      |
|                                     |     p->strokeRect(20, 20, 160, 160);            |
|                                     |     g1.setEndColor(Qt::yellow);                 |
|                                     |     p->setStrokeStyle(g1);                      |
|                                     |     p->strokeRect(40, 40, 120, 120);            |
+-------------------------------------+-------------------------------------------------+

.. |image-qcpainter-strokestyle2-webp| image:: ../../../images/qcpainter-strokestyle2.webp
