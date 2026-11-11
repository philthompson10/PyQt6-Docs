.. sip:class-description::
    :status: todo
    :brief: Brush for painting image patterns
    :digest: 496a601c8fad6e6a1e6cd0250da4ff06

:sip:ref:`~PyQt6.QtCanvasPainter.QCanvasImagePattern` is a brush for painting image patterns.

:sip:ref:`~PyQt6.QtCanvasPainter.QCanvasImagePattern` is a brush for painting image patterns. To use :sip:ref:`~PyQt6.QtCanvasPainter.QCanvasImage` as a pattern, it should have some repeat flags turned on like :sip:ref:`~PyQt6.QtCanvasPainter.QCanvasPainter.ImageFlag.Repeat`.

Here is a simple example:

::

    // Setup 2 image patterns
    static QImage image1(":/pattern2.png");
    static QImage image2(":/pattern3.png");
    auto flags = QCanvasPainter::ImageFlag::Repeat |
                 QCanvasPainter::ImageFlag::GenerateMipmaps;
    QCanvasImage bg1 = painter.addImage(image1, flags);
    QCanvasImage bg2 = painter.addImage(image2, flags);
    QCanvasImagePattern ip1(bg1, 0, 0, 64, 64);
    QCanvasImagePattern ip2(bg2, 0, 0, 32, 32);
    // Fill and stroke round rectangle with
    // these image pattern brushes.
    painter.beginPath();
    painter.roundRect(50, 50, 180, 180, 40);
    painter.setFillStyle(ip1);
    painter.setStrokeStyle(ip2);
    painter.fill();
    painter.setLineWidth(20);
    painter.stroke();

.. image:: ../../../images/imagepattern_example_1.png

**Note:** When using image patterns, images are often scaled to smaller and it can be useful to set :sip:ref:`~PyQt6.QtCanvasPainter.QCanvasPainter.ImageFlag.GenerateMipmaps` for the used :sip:ref:`~PyQt6.QtCanvasPainter.QCanvasImage` to have smooth patterns.
