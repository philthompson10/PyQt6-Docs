.. sip:method-description::
    :status: todo
    :pysig: 6a1bb6ed41f44b60e7bd83b0e9945aa7
    :realsig: (qreal, qreal)
    :digest: f9cd038722108fb695cd0279ce6505e8

Adds line segment from the last point in the path to the ( *x*, *y*) point.

+-----------------------------+--------------------------+
| |image-qcpainter-line-webp| | ::                       |
|                             |                          |
|                             |     p->beginPath();      |
|                             |     p->moveTo(20, 20);   |
|                             |     p->lineTo(140, 180); |
|                             |     p->lineTo(180, 120); |
|                             |     p->stroke();         |
+-----------------------------+--------------------------+

.. |image-qcpainter-line-webp| image:: ../../../images/qcpainter-line.webp
