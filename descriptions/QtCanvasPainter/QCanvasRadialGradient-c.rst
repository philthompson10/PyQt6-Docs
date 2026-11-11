.. sip:class-description::
    :status: todo
    :brief: Brush for radial gradient painting
    :digest: eb3109b9e1bf1992543ded9bda26da70

:sip:ref:`~PyQt6.QtCanvasPainter.QCanvasRadialGradient` is a brush for radial gradient painting.

Radial gradient interpolate colors between start and end points, creating a circle shaped gradient. The gradient is controlled with :sip:ref:`~PyQt6.QtCanvasPainter.QCanvasRadialGradient.centerPosition`, :sip:ref:`~PyQt6.QtCanvasPainter.QCanvasRadialGradient.outerRadius` and :sip:ref:`~PyQt6.QtCanvasPainter.QCanvasRadialGradient.innerRadius`.

.. image:: ../../../images/qcradialgradient-gallery.webp

Here is a simple example:

+---------------------------------------+-------------------------------------------------------+
| |image-qcradialgradient-example-webp| | ::                                                    |
|                                       |                                                       |
|                                       |     QRectF rect1(0, 0, 200, 200);                     |
|                                       |     QCanvasRadialGradient rg(rect1.center(), 0, 100); |
|                                       |     rg.setColorAt(0.0, "#fdbb2d");                    |
|                                       |     rg.setColorAt(0.6, "#b21f1f");                    |
|                                       |     rg.setColorAt(1.0, "#1a2a6c");                    |
|                                       |     p->setFillStyle(rg);                              |
|                                       |     p->fillRect(rect1);                               |
+---------------------------------------+-------------------------------------------------------+

.. |image-qcradialgradient-example-webp| image:: ../../../images/qcradialgradient-example.webp
