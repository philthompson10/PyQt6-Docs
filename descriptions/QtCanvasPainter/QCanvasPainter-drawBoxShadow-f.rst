.. sip:method-description::
    :status: todo
    :pysig: 922d86d49443bcb0b826b75b142ce42a
    :realsig: (const QCanvasBoxShadow&)
    :digest: dc31c7a82681c755bdd34dea95f8d681

Draws a box *shadow*. The shadow will be painted with position, size, color, blur etc. defined by *shadow*. Calling :sip:ref:`~PyQt6.QtCanvasPainter.QCanvasPainter.beginPath` before this method is not required.

**Note:** To visually see the area covered by drawBoxShadow(), set ``QCPAINTER_DEBUG_SHADOW_RECT`` environment variable.

+----------------------------------+-------------------------------------------------+
| |image-qcpainter-shadowbox-webp| | ::                                              |
|                                  |                                                 |
|                                  |     QRectF rect(40, 40, 120, 120);              |
|                                  |     QRectF shadowRect = rect.translated(-2, 4); |
|                                  |     QCanvasBoxShadow shadow(shadowRect);        |
|                                  |     shadow.setBlur(30);                         |
|                                  |     p->drawBoxShadow(shadow);                   |
|                                  |     p->beginPath();                             |
|                                  |     p->roundRect(rect, 30);                     |
|                                  |     p->setFillStyle("#2CDE85");                 |
|                                  |     p->fill();                                  |
+----------------------------------+-------------------------------------------------+

.. seealso:: :sip:ref:`~PyQt6.QtCanvasPainter.QCanvasBoxShadow`.

.. |image-qcpainter-shadowbox-webp| image:: ../../../images/qcpainter-shadowbox.webp
