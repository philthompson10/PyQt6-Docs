.. sip:method-description::
    :status: todo
    :pysig: 568b014a366a71095f4f9661cf095121
    :realsig: (qreal, qreal, qreal, qreal, qreal)
    :digest: f9d57c71a0230bdb90057c1ab7cbd608

Adds an arc segment at the corner defined by the last path point, and two specified points (\ *x1*, *y1* and *x2*, *y2*) with *radius*. The arc is automatically connected to the path's latest point with a straight line if necessary.

+------------------------------+-------------------------------------+
| |image-qcpainter-arcto-webp| | ::                                  |
|                              |                                     |
|                              |     p->beginPath();                 |
|                              |     p->moveTo(20, 20);              |
|                              |     p->arcTo(240, 20, 20, 220, 50); |
|                              |     p->arcTo(20, 220, 20, 20, 30);  |
|                              |     p->stroke();                    |
+------------------------------+-------------------------------------+

.. |image-qcpainter-arcto-webp| image:: ../../../images/qcpainter-arcto.webp
