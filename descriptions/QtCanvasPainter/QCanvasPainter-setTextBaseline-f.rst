.. sip:method-description::
    :status: todo
    :pysig: 41573b24ffae56bd52b4ea1094dfa86d
    :realsig: (QCanvasPainter::TextBaseline)
    :digest: 23f49c552e8bfcbb5fa64456f867d069

Sets the vertical alignment (baseline) of text to *baseline*. The default alignment is ``QCanvasPainter::TextBaseline::Alphabetic``.

+-------------------------------------+-------------------------------------------------------------------+
| |image-qcpainter-textbaseline-webp| | ::                                                                |
|                                     |                                                                   |
|                                     |     QFont font("Titillium Web", 16);                              |
|                                     |     p->setFont(font);                                             |
|                                     |     p->fillRect(0, 60, 200, 1);                                   |
|                                     |     p->fillRect(0, 140, 200, 1);                                  |
|                                     |     p->setTextBaseline(QCanvasPainter::TextBaseline::Bottom);     |
|                                     |     p->fillText("Bottom", 40, 60);                                |
|                                     |     p->setTextBaseline(QCanvasPainter::TextBaseline::Middle);     |
|                                     |     p->fillText("Middle", 100, 60);                               |
|                                     |     p->setTextBaseline(QCanvasPainter::TextBaseline::Top);        |
|                                     |     p->fillText("Top", 160, 60);                                  |
|                                     |     p->setTextBaseline(QCanvasPainter::TextBaseline::Alphabetic); |
|                                     |     p->fillText("Alphabetic", 50, 140);                           |
|                                     |     p->setTextBaseline(QCanvasPainter::TextBaseline::Hanging);    |
|                                     |     p->fillText("Hanging", 150, 140);                             |
+-------------------------------------+-------------------------------------------------------------------+

.. seealso:: :sip:ref:`~PyQt6.QtCanvasPainter.QCanvasPainter.setTextAlign`.

.. |image-qcpainter-textbaseline-webp| image:: ../../../images/qcpainter-textbaseline.webp
