.. sip:method-description::
    :status: todo
    :pysig: d41d8cd98f00b204e9800998ecf8427e
    :realsig: ()
    :digest: c057baa104786580deb26ef067f357dc

Start a hole subpath. This is equivalent to ``setPathWinding(QCanvasPainter::PathWinding::ClockWise)``)

+----------------------------------+------------------------------+
| |image-qcpainter-beginhole-webp| | ::                           |
|                                  |                              |
|                                  |     p->beginPath();          |
|                                  |     p->circle(100, 100, 80); |
|                                  |     p->beginHoleSubPath();   |
|                                  |     p->rect(60, 60, 80, 80); |
|                                  |     p->beginSolidSubPath();  |
|                                  |     p->circle(100, 100, 20); |
|                                  |     p->fill();               |
|                                  |     p->stroke();             |
+----------------------------------+------------------------------+

.. seealso:: :sip:ref:`~PyQt6.QtCanvasPainter.QCanvasPainter.beginSolidSubPath`.

.. |image-qcpainter-beginhole-webp| image:: ../../../images/qcpainter-beginhole.webp
