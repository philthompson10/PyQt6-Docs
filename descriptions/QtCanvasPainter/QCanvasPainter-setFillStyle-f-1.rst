.. sip:method-description::
    :status: todo
    :pysig: 90a04f1cd47e7fe2fc8019d75e1a1a27
    :realsig: (const QCanvasBrush&)
    :digest: 9947c0bd60bbd1a03f1c3559be7df389

Sets the fill style to *brush*. The default fill style is solid black (0, 0, 0, 1).

+-----------------------------------+------------------------------------------------+
| |image-qcpainter-fillstyle2-webp| | ::                                             |
|                                   |                                                |
|                                   |     QCanvasRadialGradient g2(140, 40, 0, 300); |
|                                   |     g2.setStartColor(QColor(44, 222, 133));    |
|                                   |     g2.setEndColor(QColor(0, 65, 74));         |
|                                   |     p->setFillStyle(g2);                       |
|                                   |     p->fillRect(20, 20, 160, 160);             |
|                                   |     g2.setCenterPosition(100, 100);            |
|                                   |     p->setFillStyle(g2);                       |
|                                   |     p->fillRect(40, 40, 120, 120);             |
+-----------------------------------+------------------------------------------------+

.. |image-qcpainter-fillstyle2-webp| image:: ../../../images/qcpainter-fillstyle2.webp
