.. sip:method-description::
    :status: todo
    :pysig: 1dde6c7e827d6c9b106850918050b6fc
    :realsig: (qreal, qreal)
    :digest: 0b5ee004691b58eb0485139ed6eb3041

Skews (shears) the current coordinate system along X axis by *angleX* and along Y axis by *angleY*. Angles are specified in radians.

+-----------------------------+----------------------------------------------+
| |image-qcpainter-skew-webp| | ::                                           |
|                             |                                              |
|                             |     QRectF rect(40, 70, 120, 60);            |
|                             |     p->translate(rect.center());             |
|                             |     p->skew(-0.6);                           |
|                             |     p->translate(-rect.center());            |
|                             |     p->beginPath();                          |
|                             |     p->roundRect(rect, 10);                  |
|                             |     p->fill();                               |
|                             |     p->stroke();                             |
|                             |     p->setFillStyle(QColorConstants::Black); |
|                             |     p->fillText("Cute!", rect);              |
+-----------------------------+----------------------------------------------+

.. |image-qcpainter-skew-webp| image:: ../../../images/qcpainter-skew.webp
