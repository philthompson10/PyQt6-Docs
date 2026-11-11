.. sip:method-description::
    :status: todo
    :pysig: 546ade640b6edfbc8a086ef31347e768
    :realsig: (qreal)
    :digest: 32857d78b0bf6088fdafe4cf485b4ca9

Sets the current antialiasing amount to *antialias* in pixels. More antialias means smoother painting. This only affects fill and stroke painting, not images or texts. The default value is ``1.0`` and the maximum value is ``10.0``.

Antialiasing can be modified per-path so it can be set before each stroke/fill. To disable antialiasing and reduce the rendering cost, set the antialias to ``0``.

+----------------------------------+-------------------------------------------+
| |image-qcpainter-antialias-webp| | ::                                        |
|                                  |                                           |
|                                  |     p->setLineWidth(6);                   |
|                                  |     for (int i = 1; i < 10 ; i++) {       |
|                                  |         int y = i * 20;                   |
|                                  |         p->setAntialias(i);               |
|                                  |         p->beginPath();                   |
|                                  |         p->moveTo(20, y);                 |
|                                  |         p->bezierCurveTo(80, y + 20, 120, |
|                                  |                          y - 20, 180, y); |
|                                  |         p->stroke();                      |
|                                  |     }                                     |
+----------------------------------+-------------------------------------------+

.. seealso:: :sip:ref:`~PyQt6.QtCanvasPainter.QCanvasPainter.setTextAntialias`.

.. |image-qcpainter-antialias-webp| image:: ../../../images/qcpainter-antialias.webp
