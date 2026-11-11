.. sip:method-description::
    :status: todo
    :pysig: 5fd70130e629f44666196fc320d4f2e1
    :realsig: (qreal, qreal, qreal, qreal)
    :digest: ea47908ae11ce35188969c446d89547b

Creates a new rectangle shaped sub-path in position *x*, *y* with size *width*, *height*.

+-----------------------------+--------------------------------+
| |image-qcpainter-rect-webp| | ::                             |
|                             |                                |
|                             |     p->beginPath();            |
|                             |     p->rect(20, 20, 160, 160); |
|                             |     p->fill();                 |
|                             |     p->stroke();               |
+-----------------------------+--------------------------------+

.. |image-qcpainter-rect-webp| image:: ../../../images/qcpainter-rect.webp
