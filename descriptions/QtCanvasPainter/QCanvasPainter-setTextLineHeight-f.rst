.. sip:method-description::
    :status: todo
    :pysig: 546ade640b6edfbc8a086ef31347e768
    :realsig: (qreal)
    :digest: b7033c0e53968f315ff3c9be0ec9b18d

Sets the line height adjustment in pixels to *height* for wrapped text. The default line height is ``0``.

+---------------------------------------+----------------------------------------------------+
| |image-qcpainter-textlineheight-webp| | ::                                                 |
|                                       |                                                    |
|                                       |     QRectF r1(40, 5, 120, 60);                     |
|                                       |     QRectF r2(40, 70, 120, 60);                    |
|                                       |     QRectF r3(40, 135, 120, 60);                   |
|                                       |     p->strokeRect(r1);                             |
|                                       |     p->strokeRect(r2);                             |
|                                       |     p->strokeRect(r3);                             |
|                                       |     p->setTextLineHeight(-10);                     |
|                                       |     p->fillText("Text with line height: -10", r1); |
|                                       |     p->setTextLineHeight(0);                       |
|                                       |     p->fillText("Text with line height: 0", r2);   |
|                                       |     p->setTextLineHeight(10);                      |
|                                       |     p->fillText("Text with line height: 10", r3);  |
+---------------------------------------+----------------------------------------------------+

.. |image-qcpainter-textlineheight-webp| image:: ../../../images/qcpainter-textlineheight.webp
