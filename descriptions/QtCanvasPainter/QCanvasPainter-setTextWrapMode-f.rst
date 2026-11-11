.. sip:method-description::
    :status: todo
    :pysig: 699fb37cbb811a930680dc1ae5751f19
    :realsig: (QCanvasPainter::WrapMode)
    :digest: be6c6a7fb7eede06db09b08785b216fe

Sets the text wrap mode to *wrapMode*. The default wrap mode is ``QCanvasPainter::WrapMode::NoWrap``.

+-------------------------------------+-----------------------------------------------------------------+
| |image-qcpainter-textwrapmode-webp| | ::                                                              |
|                                     |                                                                 |
|                                     |     QRectF r1(50, 5, 100, 60);                                  |
|                                     |     QRectF r2(50, 70, 100, 60);                                 |
|                                     |     QRectF r3(50, 135, 100, 60);                                |
|                                     |     p->strokeRect(r1);                                          |
|                                     |     p->strokeRect(r2);                                          |
|                                     |     p->strokeRect(r3);                                          |
|                                     |     QString s("This is a long string.");                        |
|                                     |     p->setTextWrapMode(QCanvasPainter::WrapMode::NoWrap);       |
|                                     |     p->fillText(s, r1);                                         |
|                                     |     p->setTextWrapMode(QCanvasPainter::WrapMode::Wrap);         |
|                                     |     p->fillText(s, r2);                                         |
|                                     |     p->setTextWrapMode(QCanvasPainter::WrapMode::WrapAnywhere); |
|                                     |     p->fillText(s, r3);                                         |
+-------------------------------------+-----------------------------------------------------------------+

.. |image-qcpainter-textwrapmode-webp| image:: ../../../images/qcpainter-textwrapmode.webp
