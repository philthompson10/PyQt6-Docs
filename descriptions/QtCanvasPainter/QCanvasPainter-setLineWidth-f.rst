.. sip:method-description::
    :status: todo
    :pysig: 546ade640b6edfbc8a086ef31347e768
    :realsig: (qreal)
    :digest: 729ef46076a88b7bc7d5e9c0777fdb5d

Sets the line width of strokes to *width* in pixels. The default line width is ``1.0``. When antialiasing is enabled, widths thinner than a single pixel will automatically fade the opacity, creating a smooth output.

+----------------------------------+-------------------------------------------+
| |image-qcpainter-linewidth-webp| | ::                                        |
|                                  |                                           |
|                                  |     for (int i = 1; i < 10 ; i++) {       |
|                                  |         int y = i * 20;                   |
|                                  |         p->setLineWidth(0.5 * i);         |
|                                  |         p->beginPath();                   |
|                                  |         p->moveTo(20, y);                 |
|                                  |         p->bezierCurveTo(80, y + 20, 120, |
|                                  |                          y - 20, 180, y); |
|                                  |         p->stroke();                      |
|                                  |     }                                     |
+----------------------------------+-------------------------------------------+

.. seealso:: :sip:ref:`~PyQt6.QtCanvasPainter.QCanvasPainter.stroke`.

.. |image-qcpainter-linewidth-webp| image:: ../../../images/qcpainter-linewidth.webp
