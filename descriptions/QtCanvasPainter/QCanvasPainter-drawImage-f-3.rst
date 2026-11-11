.. sip:method-description::
    :status: todo
    :pysig: 29b693b6f52256a1463aab645e2681a0
    :realsig: (const QCanvasImage&, qreal, qreal, qreal, qreal)
    :digest: 1f1325d9159de28786fc862f3e812f57

Draw *image* into *x*, *y*, at given *width* and *height*.

+-----------------------------------+---------------------------------------------+
| |image-qcpainter-drawimage2-webp| | ::                                          |
|                                   |                                             |
|                                   |     static QImage logo(":/qt_logo.png");    |
|                                   |     QCanvasImage image = p->addImage(logo); |
|                                   |     p->drawImage(image, 50, 0, 100, 200);   |
+-----------------------------------+---------------------------------------------+

.. seealso:: :sip:ref:`~PyQt6.QtCanvasPainter.QCanvasPainter.addImage`.

.. |image-qcpainter-drawimage2-webp| image:: ../../../images/qcpainter-drawimage2.webp
