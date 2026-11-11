.. sip:method-description::
    :status: todo
    :pysig: d41d8cd98f00b204e9800998ecf8427e
    :realsig: ()
    :digest: dec1a9ee93af72c1dc38747736daf661

Fills the current path with the current fill style, and the current fill rule.

+-----------------------------+--------------------------------+
| |image-qcpainter-fill-webp| | ::                             |
|                             |                                |
|                             |     p->beginPath();            |
|                             |     p->rect(20, 20, 40, 160);  |
|                             |     p->rect(140, 20, 40, 160); |
|                             |     p->circle(100, 100, 60);   |
|                             |     p->fill();                 |
+-----------------------------+--------------------------------+

.. seealso:: :sip:ref:`~PyQt6.QtCanvasPainter.QCanvasPainter.setFillStyle`, :sip:ref:`~PyQt6.QtCanvasPainter.QCanvasPainter.setFillRule`.

.. |image-qcpainter-fill-webp| image:: ../../../images/qcpainter-fill.webp
