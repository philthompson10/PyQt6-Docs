.. sip:method-description::
    :status: todo
    :pysig: 546ade640b6edfbc8a086ef31347e768
    :realsig: (qreal)
    :digest: d3cefa76447b14e3cde5e4ab07f70b59

Scales the current coordinate system by *scale*. Both x and y coordinates are scaled evenly.

+------------------------------+---------------------------------------+
| |image-qcpainter-scale-webp| | ::                                    |
|                              |                                       |
|                              |     QRectF rect(20, 20, 160, 160);    |
|                              |     for (int i = 0; i < 20; i++) {    |
|                              |         p->beginPath();               |
|                              |         p->roundRect(rect, 10);       |
|                              |         p->stroke();                  |
|                              |         p->translate(rect.center());  |
|                              |         p->scale(0.8);                |
|                              |         p->translate(-rect.center()); |
|                              |     }                                 |
+------------------------------+---------------------------------------+

.. |image-qcpainter-scale-webp| image:: ../../../images/qcpainter-scale.webp
