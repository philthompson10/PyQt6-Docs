.. sip:class-description::
    :status: todo
    :brief: The image class for QCanvasPainter
    :digest: 06d61ba0c0e1cc8374dc6e04f7681d0f

:sip:ref:`~PyQt6.QtCanvasPainter.QCanvasImage` is the image class for :sip:ref:`~PyQt6.QtCanvasPainter.QCanvasPainter`.

:sip:ref:`~PyQt6.QtCanvasPainter.QCanvasImage` is the image class used by :sip:ref:`~PyQt6.QtCanvasPainter.QCanvasPainter`. To be able to paint images, they fist need to be made available with e.g. :sip:ref:`~PyQt6.QtCanvasPainter.QCanvasPainter.addImage`. Then images can be painted as-is using :sip:ref:`~PyQt6.QtCanvasPainter.QCanvasPainter.drawImage` or used with :sip:ref:`~PyQt6.QtCanvasPainter.QCanvasImagePattern` brush to fill / stroke.

Here is a simple example:

::

    static QImage logoImage(":/qtlogo.png");
    // Paint an image pattern.
    QCanvasImage bg = painter.addImage(logoImage,
                 QCanvasPainter::ImageFlag::Repeat |
                 QCanvasPainter::ImageFlag::GenerateMipmaps);
    QCanvasImagePattern ip(bg, 0, 0, 44, 32);
    painter.setFillStyle(ip);
    painter.fillRect(50, 50, 320, 230);
    // Paint a single image, with tint color.
    QCanvasImage logo = painter.addImage(logoImage);
    logo.setTintColor("#2cde85");
    painter.drawImage(logo, 100, 80);

.. image:: ../../../images/image_example_1.png

In the above example the :sip:ref:`~PyQt6.QtGui.QImage` is static and addImage() is called on every repaint. This is not a problem as when the image and flags remain the same, addImage() fetches the image from cache instead of uploads it again as a texture. But a more common approac is having :sip:ref:`~PyQt6.QtCanvasPainter.QCanvasImage` variables as class members and calling :sip:ref:`~PyQt6.QtCanvasPainter.QCanvasPainter.addImage` e.g. in :sip:ref:`~PyQt6.QtCanvasPainter.QCanvasPainterItemRenderer.initializeResources`.

Similarly to :sip:ref:`~PyQt6.QtCanvasPainter.QCanvasBrush` and :sip:ref:`~PyQt6.QtCanvasPainter.QCanvasOffscreenCanvas`, :sip:ref:`~PyQt6.QtCanvasPainter.QCanvasImage` is explicitly shared. See `Implicit Data Sharing <https://doc.qt.io/qt-6/implicit-sharing.html>`_ and QSharedDataPointer for details.

**Note:** A :sip:ref:`~PyQt6.QtCanvasPainter.QCanvasImage` object contains only a handle to a graphics resource, such as a texture. Even when a detach occurs, the actual resource, i.e. the underlying texture and the image data in it, is never actually copied or duplicated. The actual owner of the real graphics resource (e.g., a :sip:ref:`~PyQt6.QtGui.QRhiTexture`) is the :sip:ref:`~PyQt6.QtCanvasPainter.QCanvasPainter` that handed out the :sip:ref:`~PyQt6.QtCanvasPainter.QCanvasImage` via :sip:ref:`~PyQt6.QtCanvasPainter.QCanvasPainter.addImage`.

A :sip:ref:`~PyQt6.QtCanvasPainter.QCanvasImage` always belongs to the :sip:ref:`~PyQt6.QtCanvasPainter.QCanvasPainter` that created it. Manually removing images is done by calling :sip:ref:`~PyQt6.QtCanvasPainter.QCanvasPainter.removeImage`. In most cases this will not be necessary, however, since the painter will automatically destroy any images during its own destruction.
