.. sip:method-description::
    :status: todo
    :pysig: 100364ab1548cfa3bd63dcad252cd771
    :realsig: (const QString&, qreal, qreal, qreal) const
    :digest: b6f212d1f0bb36fc7c3d92461d2f4750

Measures bounding box of a *text* string at (\ *x*, *y*).

To measure multi-line text, set the text wrap mode using :sip:ref:`~PyQt6.QtCanvasPainter.QCanvasPainter.setTextWrapMode` to something else than the default ``NoWrap``. Also set the optional *maxWidth* parameter to preferred row width in pixels.

Returns :sip:ref:`~PyQt6.QtCore.QRectF` with values [xmin, ymin, width, height]. Measured values are returned in local coordinate space.

+----------------------------------------+-------------------------------------------------------------+
| |image-qcpainter-textboundingbox-webp| | ::                                                          |
|                                        |                                                             |
|                                        |     QString s("Built with Qt");                             |
|                                        |     QPointF pos1(20, 20);                                   |
|                                        |     QRectF box1 = p->textBoundingBox(s, pos1);              |
|                                        |     p->strokeRect(box1);                                    |
|                                        |     p->fillText(s, pos1);                                   |
|                                        |     p->setTextWrapMode(QCanvasPainter::WrapMode::WordWrap); |
|                                        |     p->setTextAlign(QCanvasPainter::TextAlign::Center);     |
|                                        |     QPointF pos2(100, 80);                                  |
|                                        |     QRectF box2 = p->textBoundingBox(s, pos2, 100);         |
|                                        |     p->strokeRect(box2);                                    |
|                                        |     p->fillText(s, pos2, 100);                              |
+----------------------------------------+-------------------------------------------------------------+

.. |image-qcpainter-textboundingbox-webp| image:: ../../../images/qcpainter-textboundingbox.webp
