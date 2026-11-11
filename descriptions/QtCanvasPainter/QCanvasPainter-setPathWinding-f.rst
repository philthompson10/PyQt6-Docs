.. sip:method-description::
    :status: todo
    :pysig: b672a6d2bcac3519b0a368f97b80ffd1
    :realsig: (QCanvasPainter::PathWinding)
    :digest: 0364660e3f8bf8ddbce6c9a6b2c09dc9

Sets the current sub-path *winding* to either :sip:ref:`~PyQt6.QtCanvasPainter.QCanvasPainter.PathWinding.CounterClockWise` (default) or :sip:ref:`~PyQt6.QtCanvasPainter.QCanvasPainter.PathWinding.ClockWise`. :sip:ref:`~PyQt6.QtCanvasPainter.QCanvasPainter.PathWinding.CounterClockWise` draws solid subpaths while :sip:ref:`~PyQt6.QtCanvasPainter.QCanvasPainter.PathWinding.ClockWise` draws holes.

+------------------------------------+----------------------------------------------------------------+
| |image-qcpainter-pathwinding-webp| | ::                                                             |
|                                    |                                                                |
|                                    |     p->beginPath();                                            |
|                                    |     p->roundRect(20, 20, 160, 160, 40);                        |
|                                    |     p->setPathWinding(QCanvasPainter::PathWinding::ClockWise); |
|                                    |     p->circle(140, 60, 20);                                    |
|                                    |     p->rect(60, 120, 80, 30);                                  |
|                                    |     p->fill();                                                 |
|                                    |     p->stroke();                                               |
+------------------------------------+----------------------------------------------------------------+

.. seealso:: :sip:ref:`~PyQt6.QtCanvasPainter.QCanvasPainter.beginHoleSubPath`, :sip:ref:`~PyQt6.QtCanvasPainter.QCanvasPainter.beginSolidSubPath`.

.. |image-qcpainter-pathwinding-webp| image:: ../../../images/qcpainter-pathwinding.webp
