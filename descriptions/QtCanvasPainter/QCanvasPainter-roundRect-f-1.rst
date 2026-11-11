.. sip:method-description::
    :status: todo
    :pysig: 568b014a366a71095f4f9661cf095121
    :realsig: (qreal, qreal, qreal, qreal, qreal)
    :digest: 01a60438d7996d575edc8c88fc28f5d9

Creates a new rounded rectangle shaped sub-path in position *x*, *y* with size *width*, *height*. Corners rounding will be *radius*.

+----------------------------------+-----------------------------------------+
| |image-qcpainter-roundrect-webp| | ::                                      |
|                                  |                                         |
|                                  |     p->beginPath();                     |
|                                  |     p->roundRect(20, 20, 160, 160, 30); |
|                                  |     p->fill();                          |
|                                  |     p->stroke();                        |
+----------------------------------+-----------------------------------------+

.. |image-qcpainter-roundrect-webp| image:: ../../../images/qcpainter-roundrect.webp
