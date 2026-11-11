.. sip:method-description::
    :status: todo
    :pysig: 21098437f0cc089b6fbfb58aa24f7d7e
    :realsig: (const QCanvasImage&, qreal, qreal)
    :digest: 51f25c6dbeb63d2709fa8350b94c4469

Draw *image* into *x*, *y*, at its default size.

+----------------------------------+---------------------------------------------+
| |image-qcpainter-drawimage-webp| | ::                                          |
|                                  |                                             |
|                                  |     static QImage logo(":/qt_logo.png");    |
|                                  |     QCanvasImage image = p->addImage(logo); |
|                                  |     p->drawImage(image, 36, 36);            |
+----------------------------------+---------------------------------------------+

.. seealso:: :sip:ref:`~PyQt6.QtCanvasPainter.QCanvasPainter.addImage`.

.. |image-qcpainter-drawimage-webp| image:: ../../../images/qcpainter-drawimage.webp
