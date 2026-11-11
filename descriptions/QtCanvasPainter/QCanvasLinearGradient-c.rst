.. sip:class-description::
    :status: todo
    :brief: Brush for linear gradient painting
    :digest: 3032386fa381c298d2753a3a757dc659

:sip:ref:`~PyQt6.QtCanvasPainter.QCanvasLinearGradient` is a brush for linear gradient painting.

Liner gradient interpolate colors between start and end points along a linear pattern, so horizontally, vertically or diagonally. The gradient starts from *startPosition()* and ends to *endPosition()*. Outside this area, the colors are the starting and the ending color.

.. image:: ../../../images/qclineargradient-gallery.webp

Here is a simple example:

+---------------------------------------+-----------------------------------------------+
| |image-qclineargradient-example-webp| | ::                                            |
|                                       |                                               |
|                                       |     QRectF rect1(0, 0, 200, 200);             |
|                                       |     QCanvasLinearGradient lg(rect1.topLeft(), |
|                                       |                         rect1.bottomRight()); |
|                                       |     lg.setColorAt(0.0, "#1a2a6c");            |
|                                       |     lg.setColorAt(0.5, "#b21f1f");            |
|                                       |     lg.setColorAt(1.0, "#fdbb2d");            |
|                                       |     p->setFillStyle(lg);                      |
|                                       |     p->fillRect(rect1);                       |
+---------------------------------------+-----------------------------------------------+

.. |image-qclineargradient-example-webp| image:: ../../../images/qclineargradient-example.webp
