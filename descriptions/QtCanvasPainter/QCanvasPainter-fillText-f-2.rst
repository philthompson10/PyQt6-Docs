.. sip:method-description::
    :status: todo
    :pysig: 9a3df4ea685d06f84b6188c96cd46559
    :realsig: (const QString&, qreal, qreal, qreal)
    :digest: 36b45d168c8cef5cd97e6822efcc1230

Draws *text* string at the specified location ( *x*, *y*), with current textAlign and textBaseline. To make the text wrap into multiple lines, set the text wrap mode using :sip:ref:`~PyQt6.QtCanvasPainter.QCanvasPainter.setTextWrapMode` to something else than the default ``NoWrap``. Optional *maxWidth* parameter defaults to ``0``. Meaning that when e.g. ``WordWrap`` has been set, text is wrapped on every word. Set the *maxWidth* parameter to preferred row width in pixels.

+---------------------------------+---------------------------------------------------------------+
| |image-qcpainter-filltext-webp| | ::                                                            |
|                                 |                                                               |
|                                 |     p->setTextAlign(QCanvasPainter::TextAlign::Center);       |
|                                 |     p->setTextBaseline(QCanvasPainter::TextBaseline::Middle); |
|                                 |     QString text("Qt Canvas Painter");                        |
|                                 |     p->fillText(text, 100, 30);                               |
|                                 |     p->setTextWrapMode(QCanvasPainter::WrapMode::WordWrap);   |
|                                 |     p->fillText(text, 100, 90);                               |
|                                 |     p->fillText(text, 100, 160, 120);                         |
+---------------------------------+---------------------------------------------------------------+

.. seealso:: :sip:ref:`~PyQt6.QtCanvasPainter.QCanvasPainter.setTextAlign`, :sip:ref:`~PyQt6.QtCanvasPainter.QCanvasPainter.setTextBaseline`, :sip:ref:`~PyQt6.QtCanvasPainter.QCanvasPainter.setTextWrapMode`.

.. |image-qcpainter-filltext-webp| image:: ../../../images/qcpainter-filltext.webp
