.. sip:method-description::
    :status: todo
    :pysig: 566c29723d77afdf0648ce9d4c87b5ad
    :realsig: (qreal, qreal, qreal, qreal, qreal, qreal)
    :digest: 4ec8e7803411d9a38dd07bd134f44d96

Adds a cubic bezier segment from the last point in the path via two control points (\ *cp1X*, *cp1Y* and *cp2X*, *cp2Y*) to the specified point (\ *x*, *y*).

+------------------------------------+---------------------------------------------------+
| |image-qcpainter-beziercurve-webp| | ::                                                |
|                                    |                                                   |
|                                    |     p->beginPath();                               |
|                                    |     p->moveTo(20, 20);                            |
|                                    |     p->bezierCurveTo(150, 50, 50, 250, 180, 120); |
|                                    |     p->stroke();                                  |
+------------------------------------+---------------------------------------------------+

.. |image-qcpainter-beziercurve-webp| image:: ../../../images/qcpainter-beziercurve.webp
