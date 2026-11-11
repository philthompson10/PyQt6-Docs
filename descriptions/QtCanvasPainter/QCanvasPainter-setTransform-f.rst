.. sip:method-description::
    :status: todo
    :pysig: e27247e5b452ce98dcfc93f19679f890
    :realsig: (const QTransform&)
    :digest: 090c413c3f5fdc705d71ecb532465855

Resets the current transform and uses *transform* instead.

+----------------------------------+---------------------------------------+
| |image-qcpainter-transform-webp| | ::                                    |
|                                  |                                       |
|                                  |     p->beginPath();                   |
|                                  |     p->roundRect(80, 20, 40, 40, 10); |
|                                  |     p->fill();                        |
|                                  |     p->stroke();                      |
|                                  |     QTransform t;                     |
|                                  |     t.translate(100, 20);             |
|                                  |     t.rotate(45);                     |
|                                  |     t.scale(2.0, 2.0);                |
|                                  |     p->setTransform(t);               |
|                                  |     p->beginPath();                   |
|                                  |     p->roundRect(20, 20, 40, 40, 10); |
|                                  |     p->fill();                        |
|                                  |     p->stroke();                      |
+----------------------------------+---------------------------------------+

.. seealso:: :sip:ref:`~PyQt6.QtCanvasPainter.QCanvasPainter.transform`.

.. |image-qcpainter-transform-webp| image:: ../../../images/qcpainter-transform.webp
