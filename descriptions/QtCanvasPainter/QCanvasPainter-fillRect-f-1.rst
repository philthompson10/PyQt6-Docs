.. sip:method-description::
    :status: todo
    :pysig: 5fd70130e629f44666196fc320d4f2e1
    :realsig: (qreal, qreal, qreal, qreal)
    :digest: c5be7638b716c162cd734f3a401c3729

Draws a filled rectangle into the specified position ( *x*, *y*) with size *width*, *height*.

**Note:** This is provided for convenience. When filling more than just a single rect, prefer using :sip:ref:`~PyQt6.QtCanvasPainter.QCanvasPainter.rect`.

+---------------------------------+-------------------------------------+
| |image-qcpainter-fillrect-webp| | ::                                  |
|                                 |                                     |
|                                 |     p->fillRect(20, 20, 160, 160);  |
|                                 |     // The above code does same as: |
|                                 |     //  p->beginPath();             |
|                                 |     //  p->rect(20, 20, 160, 160);  |
|                                 |     //  p->fill();                  |
+---------------------------------+-------------------------------------+

.. |image-qcpainter-fillrect-webp| image:: ../../../images/qcpainter-fillrect.webp
