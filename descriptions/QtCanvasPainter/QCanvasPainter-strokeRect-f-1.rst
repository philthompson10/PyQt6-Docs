.. sip:method-description::
    :status: todo
    :pysig: 5fd70130e629f44666196fc320d4f2e1
    :realsig: (qreal, qreal, qreal, qreal)
    :digest: 48adeae88a7df0e67b208a63ba62f2aa

Draws a stroked rectangle into the specified position ( *x*, *y*) with size *width*, *height*.

**Note:** This is provided for convenience. When stroking more than just a single rect, prefer using :sip:ref:`~PyQt6.QtCanvasPainter.QCanvasPainter.rect`.

+-----------------------------------+--------------------------------------+
| |image-qcpainter-strokerect-webp| | ::                                   |
|                                   |                                      |
|                                   |     p->strokeRect(20, 20, 160, 160); |
|                                   |     // The above code does same as:  |
|                                   |     // p->beginPath();               |
|                                   |     // p->rect(20, 20, 160, 160);    |
|                                   |     // p->stroke();                  |
+-----------------------------------+--------------------------------------+

.. |image-qcpainter-strokerect-webp| image:: ../../../images/qcpainter-strokerect.webp
