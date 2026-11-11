.. sip:method-description::
    :status: todo
    :pysig: 546ade640b6edfbc8a086ef31347e768
    :realsig: (qreal)
    :digest: ba60b711dfaba0b1921e812518539c8b

Sets the global contrast to *value*. This contrast is applied to all rendered shapes. A value of 0 will cause painting to be completely gray (0.5, 0.5, 0.5). Value can also be bigger than 1.0, to increase the contrast. By default, contrast is ``1.0``.

+---------------------------------------+-----------------------------------------------+
| |image-qcpainter-globalcontrast-webp| | ::                                            |
|                                       |                                               |
|                                       |     static QImage logo(":/qt_logo2.png");     |
|                                       |     QCanvasImage image = p->addImage(logo);   |
|                                       |     p->setFillStyle("#d9f720");               |
|                                       |     for (int i = 0; i < 4; i++) {             |
|                                       |         qreal x = 100 * (i % 2);              |
|                                       |         qreal y = 100 * (i / 2);              |
|                                       |         QRectF rect(x, y, 100, 100);          |
|                                       |         p->setGlobalContrast(1.5 - i * 0.45); |
|                                       |         p->fillRect(rect);                    |
|                                       |         p->drawImage(image, rect);            |
|                                       |     }                                         |
+---------------------------------------+-----------------------------------------------+

.. |image-qcpainter-globalcontrast-webp| image:: ../../../images/qcpainter-globalcontrast.webp
