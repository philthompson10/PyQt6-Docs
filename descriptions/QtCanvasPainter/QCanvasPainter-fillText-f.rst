.. sip:method-description::
    :status: todo
    :pysig: 2a29f8f4de51d72ba6531f5e51400657
    :realsig: (const QString&, const QRectF&)
    :digest: 85202d2016e046fdee813b35fcc36fb5

Draws *text* string inside *rect*, with current textAlign and textBaseline. Width of the rect parameter is used as maxWidth.

This is an overloaded method using :sip:ref:`~PyQt6.QtCore.QRectF`. It is often useful to set the text baseline to :sip:ref:`~PyQt6.QtCanvasPainter.QCanvasPainter.TextBaseline.Top` or :sip:ref:`~PyQt6.QtCanvasPainter.QCanvasPainter.TextBaseline.Middle` when painting text with this method.

+----------------------------------+---------------------------------------------------------------+
| |image-qcpainter-filltext2-webp| | ::                                                            |
|                                  |                                                               |
|                                  |     p->setTextAlign(QCanvasPainter::TextAlign::Center);       |
|                                  |     p->setTextBaseline(QCanvasPainter::TextBaseline::Middle); |
|                                  |     QString text("Qt Canvas Painter");                        |
|                                  |     QRectF rect1(10, 20, 180, 50);                            |
|                                  |     p->strokeRect(rect1);                                     |
|                                  |     p->fillText(text, rect1);                                 |
|                                  |     p->setTextWrapMode(QCanvasPainter::WrapMode::WordWrap);   |
|                                  |     QRectF rect2(60, 90, 80, 90);                             |
|                                  |     p->strokeRect(rect2);                                     |
|                                  |     p->fillText(text, rect2);                                 |
+----------------------------------+---------------------------------------------------------------+

.. seealso:: :sip:ref:`~PyQt6.QtCanvasPainter.QCanvasPainter.setTextAlign`, :sip:ref:`~PyQt6.QtCanvasPainter.QCanvasPainter.setTextBaseline`, :sip:ref:`~PyQt6.QtCanvasPainter.QCanvasPainter.setTextWrapMode`.

.. |image-qcpainter-filltext2-webp| image:: ../../../images/qcpainter-filltext2.webp
