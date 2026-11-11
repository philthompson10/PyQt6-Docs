.. sip:method-description::
    :status: todo
    :pysig: 5fd70130e629f44666196fc320d4f2e1
    :realsig: (qreal, qreal, qreal, qreal)
    :digest: 96fd6c2ad5eb336282d08694128fa459

Erases the pixels in a rectangular area by filling the rectangle specified by *x*, *y*, *width*, *height* with transparent black. As clearing does not need blending, it can be faster than :sip:ref:`~PyQt6.QtCanvasPainter.QCanvasPainter.fillRect`.

+----------------------------------+-----------------------------------+
| |image-qcpainter-clearrect-webp| | ::                                |
|                                  |                                   |
|                                  |     p->beginPath();               |
|                                  |     p->circle(100, 100, 80);      |
|                                  |     p->fill();                    |
|                                  |     p->stroke();                  |
|                                  |     p->clearRect(60, 0, 80, 120); |
+----------------------------------+-----------------------------------+

.. |image-qcpainter-clearrect-webp| image:: ../../../images/qcpainter-clearrect.webp
