.. sip:method-description::
    :status: todo
    :pysig: d41d8cd98f00b204e9800998ecf8427e
    :realsig: ()
    :digest: d97328759bce4c7d237c48d926ae3405

Strokes the current path with the current stroke style.

+-------------------------------+--------------------------------+
| |image-qcpainter-stroke-webp| | ::                             |
|                               |                                |
|                               |     p->beginPath();            |
|                               |     p->rect(20, 20, 40, 160);  |
|                               |     p->rect(140, 20, 40, 160); |
|                               |     p->circle(100, 100, 60);   |
|                               |     p->stroke();               |
+-------------------------------+--------------------------------+

.. seealso:: :sip:ref:`~PyQt6.QtCanvasPainter.QCanvasPainter.setStrokeStyle`.

.. |image-qcpainter-stroke-webp| image:: ../../../images/qcpainter-stroke.webp
