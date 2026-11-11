.. sip:class-description::
    :status: todo
    :brief: Represents an offscreen canvas that QCanvasPainter can target
    :digest: 77f65e8ba9003b3a63c5a537a05061b9

:sip:ref:`~PyQt6.QtCanvasPainter.QCanvasOffscreenCanvas` represents an offscreen canvas that :sip:ref:`~PyQt6.QtCanvasPainter.QCanvasPainter` can target.

An offscreen canvas is essentially a color buffer (a :sip:ref:`~PyQt6.QtGui.QRhiTexture`), and possibly other associated graphics resources. After content has been rendered into the canvas's color buffer, the canvas can be :sip:ref:`~PyQt6.QtCanvasPainter.QCanvasPainter.addImage` to the painter to retrieve a :sip:ref:`~PyQt6.QtCanvasPainter.QCanvasImage` that can then be used in :sip:ref:`~PyQt6.QtCanvasPainter.QCanvasPainter.drawImage` calls or as an :sip:ref:`~PyQt6.QtCanvasPainter.QCanvasImagePattern`.

To create an offscreen canvas, call :sip:ref:`~PyQt6.QtCanvasPainter.QCanvasPainter.createCanvas`. To target an offscreen canvas with with draw commands, call the appropriate QCanvasRhiPaintDriver::beginPaint() overload when working with the lower level API, or :sip:ref:`~PyQt6.QtCanvasPainter.QCanvasPainterWidget.beginCanvasPainting` or :sip:ref:`~PyQt6.QtCanvasPainter.QCanvasPainterItemRenderer.beginCanvasPainting` when using the convenience widget or Qt Quick item classes.

Similarly to :sip:ref:`~PyQt6.QtCanvasPainter.QCanvasImage` and :sip:ref:`~PyQt6.QtCanvasPainter.QCanvasBrush`, :sip:ref:`~PyQt6.QtCanvasPainter.QCanvasOffscreenCanvas` is explicitly shared. See `Implicit Data Sharing <https://doc.qt.io/qt-6/implicit-sharing.html>`_ and QSharedDataPointer for details.

**Note:** As with :sip:ref:`~PyQt6.QtCanvasPainter.QCanvasImage`, a :sip:ref:`~PyQt6.QtCanvasPainter.QCanvasOffscreenCanvas` can be seen as an object merely containing handles. Even when a detach occurs, the actual resources, e.g. the underlying texture and the image data in it, are never actually copied or duplicated. The actual owner of any real graphics resources (e.g., a :sip:ref:`~PyQt6.QtGui.QRhiTexture`) is the :sip:ref:`~PyQt6.QtCanvasPainter.QCanvasPainter` that handed out the :sip:ref:`~PyQt6.QtCanvasPainter.QCanvasOffscreenCanvas` via :sip:ref:`~PyQt6.QtCanvasPainter.QCanvasPainter.createCanvas`.

A canvas always belongs to the :sip:ref:`~PyQt6.QtCanvasPainter.QCanvasPainter` that created it. Manually destroying canvases is done by calling :sip:ref:`~PyQt6.QtCanvasPainter.QCanvasPainter.destroyCanvas`. In most cases this will not be necessary, however, since the painter will automatically destroy any canvases during its own destruction.
