.. sip:method-description::
    :status: todo
    :pysig: d19ddfc58dc7757cd9b6a7824fbeee78
    :realsig: (QCanvasPainter::TextDirection)
    :digest: 9160abdd955057095112ffa4aa8f6083

Sets the direction of text to *direction*. The default direction is ``QCanvasPainter::TextDirection::Inherit``.

+--------------------------------------+----------------------------------------------------------------------+
| |image-qcpainter-textdirection-webp| | ::                                                                   |
|                                      |                                                                      |
|                                      |     p->setTextAlign(QCanvasPainter::TextAlign::Center);              |
|                                      |     p->setTextBaseline(QCanvasPainter::TextBaseline::Middle);        |
|                                      |     QFont font("Titillium Web", 32);                                 |
|                                      |     p->setFont(font);                                                |
|                                      |     p->setFillStyle(QColorConstants::Black);                         |
|                                      |     p->fillText("Hi!", 100, 50);                                     |
|                                      |     p->setTextDirection(QCanvasPainter::TextDirection::RightToLeft); |
|                                      |     p->fillText("Hi!", 100, 150);                                    |
+--------------------------------------+----------------------------------------------------------------------+

.. |image-qcpainter-textdirection-webp| image:: ../../../images/qcpainter-textdirection.webp
