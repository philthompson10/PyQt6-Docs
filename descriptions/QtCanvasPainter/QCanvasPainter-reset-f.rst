.. sip:method-description::
    :status: todo
    :pysig: d41d8cd98f00b204e9800998ecf8427e
    :realsig: ()
    :digest: b179add7165a241100311f6cb365e7be

Resets the current painter state to default values.

This includes the stroke and fill styles and the related properties, the transformation matrix, the clipping region, the text-related settings, the compositing properties, the drawing state stack, the antialiasing settings.

**Note:** This method differs from the HTML Canvas 2D Context reset() method in that it doesn't visually clear the canvas buffers.

**Note:** The values of :sip:ref:`~PyQt6.QtCanvasPainter.QCanvasPainter.setWindingEnforce` and :sip:ref:`~PyQt6.QtCanvasPainter.QCanvasPainter.setHighQualityStroking` are not changed.

+------------------------------+----------------------------------------+
| |image-qcpainter-reset-webp| | ::                                     |
|                              |                                        |
|                              |     // Adjust the paint state          |
|                              |     p->setStrokeStyle("#00414A");      |
|                              |     p->setFillStyle("#2CDE85");        |
|                              |     p->setLineWidth(10);               |
|                              |     QRectF rect(20, 40, 160, 50);      |
|                              |     p->translate(rect.center());       |
|                              |     p->rotate(qDegreesToRadians(-25)); |
|                              |     p->translate(-rect.center());      |
|                              |     p->beginPath();                    |
|                              |     p->roundRect(rect, 20);            |
|                              |     p->fill();                         |
|                              |     p->stroke();                       |
|                              |     // Reset to default paint state    |
|                              |     p->reset();                        |
|                              |     p->fillRect(20, 140, 60, 40);      |
|                              |     p->strokeRect(120, 140, 60, 40);   |
+------------------------------+----------------------------------------+

.. seealso:: :sip:ref:`~PyQt6.QtCanvasPainter.QCanvasPainter.save`, :sip:ref:`~PyQt6.QtCanvasPainter.QCanvasPainter.restore`.

.. |image-qcpainter-reset-webp| image:: ../../../images/qcpainter-reset.webp
