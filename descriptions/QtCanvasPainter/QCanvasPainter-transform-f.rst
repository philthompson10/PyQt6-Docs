.. sip:method-description::
    :status: todo
    :pysig: e27247e5b452ce98dcfc93f19679f890
    :realsig: (const QTransform&)
    :digest: 0bd1a27e3eb175422ac5c1dc97e06bf4

Multiplies the current coordinate system by the specified *transform*.

+-----------------------------------+-------------------------------------------+
| |image-qcpainter-transform2-webp| | ::                                        |
|                                   |                                           |
|                                   |     QTransform t;                         |
|                                   |     t.translate(100, 100);                |
|                                   |     t.rotate(36);                         |
|                                   |     t.translate(-100, -100);              |
|                                   |     for (int i = 0; i < 10; i++) {        |
|                                   |         p->transform(t);                  |
|                                   |         p->beginPath();                   |
|                                   |         p->roundRect(80, 15, 40, 20, 10); |
|                                   |         p->fill();                        |
|                                   |         p->stroke();                      |
|                                   |     }                                     |
+-----------------------------------+-------------------------------------------+

.. seealso:: :sip:ref:`~PyQt6.QtCanvasPainter.QCanvasPainter.setTransform`.

.. |image-qcpainter-transform2-webp| image:: ../../../images/qcpainter-transform2.webp
