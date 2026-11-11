.. sip:class-description::
    :status: todo
    :brief: Brush for painting grid patterns
    :digest: 26fac5f8792884af5760ef5058498ceb

:sip:ref:`~PyQt6.QtCanvasPainter.QCanvasGridPattern` is a brush for painting grid patterns.

:sip:ref:`~PyQt6.QtCanvasPainter.QCanvasGridPattern` is a brush for painting grid and bar patterns.

Here is a simple example:

::

    // Rotated grid into background
    QRectF rect(20, 20, 180, 180);
    QCanvasGridPattern gp1(rect.topLeft(), QSizeF(16, 16));
    gp1.setLineColor("#DBEB00");
    gp1.setBackgroundColor("#373F26");
    gp1.setLineWidth(2.0);
    gp1.setRotation(M_PI / 4);
    gp1.setFeather(5.0);
    painter.setFillStyle(gp1);
    painter.fillRect(rect);
    // Rounded rectangle, stroked with
    // grid pattern for dashes.
    qreal strokeW = 10;
    QRectF rect2(40, 40, 140, 140);
    QCanvasGridPattern gp2;
    gp2.setLineColor(Qt::transparent);
    gp2.setBackgroundColor(Qt::white);
    gp2.setStartPosition(rect2.x() - strokeW,
                         rect2.y() - strokeW);
    gp2.setCellSize(40, 40);
    gp2.setLineWidth(strokeW);
    painter.setLineWidth(8);
    painter.setStrokeStyle(gp2);
    painter.beginPath();
    painter.roundRect(rect2, 10);
    painter.stroke();

.. image:: ../../../images/gridpattern_example_1.png
