.. sip:method-description::
    :status: todo
    :pysig: 5fd70130e629f44666196fc320d4f2e1
    :realsig: (qreal, qreal, qreal, qreal)
    :digest: 20e9955780d0f853b48e21a8115bb755

Creates a new ellipse shaped sub-path centered at ( *centerX*, *centerY*) with *radiusX* and *radiusY*.

+--------------------------------+-----------------------------------+
| |image-qcpainter-ellipse-webp| | ::                                |
|                                |                                   |
|                                |     p->beginPath();               |
|                                |     p->ellipse(100, 100, 80, 60); |
|                                |     p->fill();                    |
|                                |     p->stroke();                  |
+--------------------------------+-----------------------------------+

.. |image-qcpainter-ellipse-webp| image:: ../../../images/qcpainter-ellipse.webp
