.. sip:class-description::
    :status: todo
    :brief: Brush for conical gradient painting
    :digest: d6ab4dec7a0d4d9745153cd00dea38a0

:sip:ref:`~PyQt6.QtCanvasPainter.QCanvasConicalGradient` is a brush for conical gradient painting.

Conical gradient interpolate colors between start and end points around a point with given coordinates. The angle starts from a line going horizontally right from the center, and proceeds clockwise.

.. image:: ../../../images/qcconicalgradient-gallery.webp

Here is a simple example:

+----------------------------------------+------------------------------------------------------------+
| |image-qcconicalgradient-example-webp| | ::                                                         |
|                                        |                                                            |
|                                        |     QRectF rect(20, 20, 160, 160);                         |
|                                        |     QCanvasConicalGradient cg(rect.center(), 1.75 * M_PI); |
|                                        |     cg.setColorAt(0.0, "#fdbb2d");                         |
|                                        |     cg.setColorAt(0.5, "#1a2a6c");                         |
|                                        |     cg.setColorAt(1.0, "#fdbb2d");                         |
|                                        |     p->setFillStyle(cg);                                   |
|                                        |     p->beginPath();                                        |
|                                        |     p->ellipse(rect);                                      |
|                                        |     p->fill();                                             |
+----------------------------------------+------------------------------------------------------------+

.. |image-qcconicalgradient-example-webp| image:: ../../../images/qcconicalgradient-example.webp
