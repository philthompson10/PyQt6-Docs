.. sip:method-description::
    :status: todo
    :pysig: 366df3fe804d1eeb758b4f25ea84eee2
    :realsig: (qreal, qreal, qreal, qreal, qreal, qreal, qreal, qreal)
    :digest: c3c38e229253ab72a15a729ccca6fdb6

Creates a new rounded rectangle shaped sub-path in position *x*, *y* with size *width*, *height*. Corners rounding can be varying per-corner, with *radiusTopLeft*, *radiusTopRight*, *radiusBottomRight*, *radiusBottomLeft*.

+-----------------------------------+------------------------------------+
| |image-qcpainter-roundrect2-webp| | ::                                 |
|                                   |                                    |
|                                   |     p->beginPath();                |
|                                   |     p->roundRect(20, 20, 160, 160, |
|                                   |                  0, 40, 20, 80);   |
|                                   |     p->fill();                     |
|                                   |     p->stroke();                   |
+-----------------------------------+------------------------------------+

.. |image-qcpainter-roundrect2-webp| image:: ../../../images/qcpainter-roundrect2.webp
