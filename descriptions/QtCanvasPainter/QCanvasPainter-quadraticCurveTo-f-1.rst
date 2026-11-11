.. sip:method-description::
    :status: todo
    :pysig: 5fd70130e629f44666196fc320d4f2e1
    :realsig: (qreal, qreal, qreal, qreal)
    :digest: 70c1ef48ddd5d57da1376cfc6d439f2c

Adds a quadratic bezier segment from the last point in the path via a control point (\ *cpX*, *cpY*) to the specified point (\ *x*, *y*).

+---------------------------------------+---------------------------------------------+
| |image-qcpainter-quadraticcurve-webp| | ::                                          |
|                                       |                                             |
|                                       |     p->beginPath();                         |
|                                       |     p->moveTo(20, 20);                      |
|                                       |     p->quadraticCurveTo(150, 50, 180, 180); |
|                                       |     p->quadraticCurveTo(20, 220, 20, 20);   |
|                                       |     p->fill();                              |
|                                       |     p->stroke();                            |
+---------------------------------------+---------------------------------------------+

.. |image-qcpainter-quadraticcurve-webp| image:: ../../../images/qcpainter-quadraticcurve.webp
