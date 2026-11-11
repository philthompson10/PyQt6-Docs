.. sip:method-description::
    :status: todo
    :pysig: 546ade640b6edfbc8a086ef31347e768
    :realsig: (qreal)
    :digest: e12ad4cc037365422fdad35aa8cf0de9

Sets the global brightness to *value*. This brightness is applied to all rendered shapes. A value of 0 will cause painting to be completely black. Value can also be bigger than 1.0, to increase the brightness. By default, brightness is ``1.0``.

+-----------------------------------------+-------------------------------------------------+
| |image-qcpainter-globalbrightness-webp| | ::                                              |
|                                         |                                                 |
|                                         |     static QImage logo(":/qt_logo2.png");       |
|                                         |     QCanvasImage image = p->addImage(logo);     |
|                                         |     p->setFillStyle("#d9f720");                 |
|                                         |     for (int i = 0; i < 4; i++) {               |
|                                         |         qreal x = 100 * (i % 2);                |
|                                         |         qreal y = 100 * (i / 2);                |
|                                         |         QRectF rect(x, y, 100, 100);            |
|                                         |         p->setGlobalBrightness(1.5 - i * 0.45); |
|                                         |         p->fillRect(rect);                      |
|                                         |         p->drawImage(image, rect);              |
|                                         |     }                                           |
+-----------------------------------------+-------------------------------------------------+

.. |image-qcpainter-globalbrightness-webp| image:: ../../../images/qcpainter-globalbrightness.webp
