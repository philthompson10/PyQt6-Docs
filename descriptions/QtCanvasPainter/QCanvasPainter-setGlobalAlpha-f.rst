.. sip:method-description::
    :status: todo
    :pysig: 546ade640b6edfbc8a086ef31347e768
    :realsig: (qreal)
    :digest: 3f6b1b7ccb7c6ef10d01c7454aa43d76

Sets the global alpha (transparency) value to *alpha*. This alpha value is applied to all rendered shapes. Already transparent paths will get proportionally more transparent as well. Alpha should be between 0.0 (fully transparent) and 1.0 (fully opaque). By default alpha is ``1.0``.

+------------------------------------+---------------------------------------------+
| |image-qcpainter-globalalpha-webp| | ::                                          |
|                                    |                                             |
|                                    |     static QImage logo(":/qt_logo2.png");   |
|                                    |     QCanvasImage image = p->addImage(logo); |
|                                    |     p->setFillStyle("#d9f720");             |
|                                    |     for (int i = 0; i < 4; i++) {           |
|                                    |         qreal x = 100 * (i % 2);            |
|                                    |         qreal y = 100 * (i / 2);            |
|                                    |         QRectF rect(x, y, 100, 100);        |
|                                    |         p->setGlobalAlpha(1.0 - i * 0.3);   |
|                                    |         p->fillRect(rect);                  |
|                                    |         p->drawImage(image, rect);          |
|                                    |     }                                       |
+------------------------------------+---------------------------------------------+

.. |image-qcpainter-globalalpha-webp| image:: ../../../images/qcpainter-globalalpha.webp
