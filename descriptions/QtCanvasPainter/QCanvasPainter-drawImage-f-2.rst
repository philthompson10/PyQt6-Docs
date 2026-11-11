.. sip:method-description::
    :status: todo
    :pysig: 8b14a9823fc91394e5062211355021d4
    :realsig: (const QCanvasImage&, const QRectF&, const QRectF&)
    :digest: 1e6de50c8d2e491ceebb8dfcb725cfba

Draw *image* into position and size of *destinationRect*, from *sourceRect* area of image.

+-----------------------------------+-------------------------------------------------------+
| |image-qcpainter-drawimage3-webp| | ::                                                    |
|                                   |                                                       |
|                                   |     static QImage logo(":/qt_logo.png");              |
|                                   |     QCanvasImage image = p->addImage(logo);           |
|                                   |     QRectF sourceRect(20, 30, 54, 76);                |
|                                   |     QRectF destinationRect(0, 0, 200, 200);           |
|                                   |     p->drawImage(image, sourceRect, destinationRect); |
+-----------------------------------+-------------------------------------------------------+

.. seealso:: :sip:ref:`~PyQt6.QtCanvasPainter.QCanvasPainter.addImage`.

.. |image-qcpainter-drawimage3-webp| image:: ../../../images/qcpainter-drawimage3.webp
