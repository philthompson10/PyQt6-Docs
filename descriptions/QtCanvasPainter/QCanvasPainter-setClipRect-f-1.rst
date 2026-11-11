.. sip:method-description::
    :status: todo
    :pysig: 5fd70130e629f44666196fc320d4f2e1
    :realsig: (qreal, qreal, qreal, qreal)
    :digest: c2e9ec7b68022a7120c9d145abe0ca41

Sets the current scissor rectangle to (\ *x*, *y*, *width*, *height*). The scissor rectangle is transformed by the current transform.

**Note:** Clipping has some performance cost and it should only be used when needed.

+---------------------------------+-----------------------------------------+
| |image-qcpainter-cliprect-webp| | ::                                      |
|                                 |                                         |
|                                 |     QRectF viewArea(20, 20, 160, 160);  |
|                                 |     p->setClipRect(viewArea);           |
|                                 |     p->beginPath();                     |
|                                 |     p->circle(40, 40, 110);             |
|                                 |     p->fill();                          |
|                                 |     p->setFillStyle(Qt::black);         |
|                                 |     p->fillText("Clip me...", 40, 100); |
|                                 |     p->strokeRect(viewArea);            |
+---------------------------------+-----------------------------------------+

.. seealso:: :sip:ref:`~PyQt6.QtCanvasPainter.QCanvasPainter.resetClipping`.

.. |image-qcpainter-cliprect-webp| image:: ../../../images/qcpainter-cliprect.webp
