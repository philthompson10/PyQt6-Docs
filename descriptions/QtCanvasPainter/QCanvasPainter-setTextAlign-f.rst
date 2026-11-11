.. sip:method-description::
    :status: todo
    :pysig: deacde50954aa6d01d50606ce0ee575d
    :realsig: (QCanvasPainter::TextAlign)
    :digest: 5f1c6e95ca5c1a85c1d0a12c3cf6602e

Sets the horizontal alignment of text to *align*. The default alignment is ``QCanvasPainter::TextAlign::Start``.

+----------------------------------+---------------------------------------------------------+
| |image-qcpainter-textalign-webp| | ::                                                      |
|                                  |                                                         |
|                                  |     QFont font("Titillium Web", 22);                    |
|                                  |     p->setFont(font);                                   |
|                                  |     p->fillRect(100, 0, 1, 200);                        |
|                                  |     p->setTextAlign(QCanvasPainter::TextAlign::Left);   |
|                                  |     p->fillText("Left", 100, 40);                       |
|                                  |     p->setTextAlign(QCanvasPainter::TextAlign::Center); |
|                                  |     p->fillText("Center", 100, 70);                     |
|                                  |     p->setTextAlign(QCanvasPainter::TextAlign::Right);  |
|                                  |     p->fillText("Right", 100, 100);                     |
|                                  |     p->setTextAlign(QCanvasPainter::TextAlign::Start);  |
|                                  |     p->fillText("Start", 100, 130);                     |
|                                  |     p->setTextAlign(QCanvasPainter::TextAlign::End);    |
|                                  |     p->fillText("End", 100, 160);                       |
+----------------------------------+---------------------------------------------------------+

.. seealso:: :sip:ref:`~PyQt6.QtCanvasPainter.QCanvasPainter.setTextBaseline`.

.. |image-qcpainter-textalign-webp| image:: ../../../images/qcpainter-textalign.webp
