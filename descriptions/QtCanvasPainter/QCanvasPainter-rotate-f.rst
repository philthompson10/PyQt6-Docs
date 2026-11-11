.. sip:method-description::
    :status: todo
    :pysig: 546ade640b6edfbc8a086ef31347e768
    :realsig: (qreal)
    :digest: 5bbdf6fc63da7a796956dd3739ccd4b5

Rotates the current coordinate system clockwise by *angle*.

The angle is specified in radians. Use qDegreesToRadians() to convert from degrees to radians.

+-------------------------------+----------------------------------------------+
| |image-qcpainter-rotate-webp| | ::                                           |
|                               |                                              |
|                               |     QRectF rect(20, 70, 160, 60);            |
|                               |     p->translate(rect.center());             |
|                               |     p->rotate(-M_PI / 4);                    |
|                               |     p->translate(-rect.center());            |
|                               |     p->beginPath();                          |
|                               |     p->roundRect(rect, 10);                  |
|                               |     p->fill();                               |
|                               |     p->stroke();                             |
|                               |     p->setFillStyle(QColorConstants::Black); |
|                               |     p->fillText("Cute!", rect);              |
+-------------------------------+----------------------------------------------+

.. |image-qcpainter-rotate-webp| image:: ../../../images/qcpainter-rotate.webp
