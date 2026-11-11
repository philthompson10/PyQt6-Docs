.. sip:class-description::
    :status: todo
    :brief: Brush for box gradient painting
    :digest: 693f6f286be56a1e58b7b1c2946534ab

:sip:ref:`~PyQt6.QtCanvasPainter.QCanvasBoxGradient` is a brush for box gradient painting.

Box gradient interpolate colors between start and end points, creating a rounded rectangle shaped gradient. With the :sip:ref:`~PyQt6.QtCanvasPainter.QCanvasBoxGradient.setRadius` and :sip:ref:`~PyQt6.QtCanvasPainter.QCanvasBoxGradient.setFeather` the roundness and softness of the gradient can be controlled.

.. image:: ../../../images/qcboxgradient-gallery.webp

Here is a simple example:

+------------------------------------+-------------------------------------------------------+
| |image-qcboxgradient-example-webp| | ::                                                    |
|                                    |                                                       |
|                                    |     QRectF rect(20, 20, 160, 160);                    |
|                                    |     QCanvasBoxGradient bg(rect);                      |
|                                    |     bg.setFeather(20);                                |
|                                    |     bg.setRadius(50);                                 |
|                                    |     bg.setColorAt(0.0, "#1a2a6c");                    |
|                                    |     bg.setColorAt(0.2, "#fdbb2d");                    |
|                                    |     bg.setColorAt(1.0, QColorConstants::Transparent); |
|                                    |     p->setFillStyle(bg);                              |
|                                    |     p->fillRect(rect);                                |
+------------------------------------+-------------------------------------------------------+

**Note:** When :sip:ref:`~PyQt6.QtCanvasPainter.QCanvasBoxGradient` is used to paint round rectangle, it is usually better to use :sip:ref:`~PyQt6.QtCanvasPainter.QCanvasPainter.rect` than :sip:ref:`~PyQt6.QtCanvasPainter.QCanvasPainter.roundRect` as the rounding comes from the brush rather than the path. This avoids creating extra vertices and thus performs better.

.. |image-qcboxgradient-example-webp| image:: ../../../images/qcboxgradient-example.webp
