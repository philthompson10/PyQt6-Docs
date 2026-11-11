.. sip:method-description::
    :status: todo
    :pysig: 546ade640b6edfbc8a086ef31347e768
    :realsig: (qreal)
    :digest: 3ddf72b76c7da406dd979fc32b0fa0af

Sets the global saturation to *value*. This saturation is applied to all rendered shapes. A value of 0 will disable saturation and cause painting to be completely grayscale. Value can also be bigger than 1.0, to increase the saturation. By default, saturation is ``1.0``.

+-----------------------------------------+------------------------------------------------+
| |image-qcpainter-globalsaturation-webp| | ::                                             |
|                                         |                                                |
|                                         |     static QImage logo(":/qt_logo2.png");      |
|                                         |     QCanvasImage image = p->addImage(logo);    |
|                                         |     p->setFillStyle("#d9f720");                |
|                                         |     for (int i = 0; i < 4; i++) {              |
|                                         |         qreal x = 100 * (i % 2);               |
|                                         |         qreal y = 100 * (i / 2);               |
|                                         |         QRectF rect(x, y, 100, 100);           |
|                                         |         p->setGlobalSaturation(1.5 - i * 0.5); |
|                                         |         p->fillRect(rect);                     |
|                                         |         p->drawImage(image, rect);             |
|                                         |     }                                          |
+-----------------------------------------+------------------------------------------------+

.. |image-qcpainter-globalsaturation-webp| image:: ../../../images/qcpainter-globalsaturation.webp
