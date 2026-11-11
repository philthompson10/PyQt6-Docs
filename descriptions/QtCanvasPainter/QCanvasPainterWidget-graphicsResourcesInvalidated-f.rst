.. sip:method-description::
    :status: todo
    :pysig: d41d8cd98f00b204e9800998ecf8427e
    :realsig: ()
    :digest: 11c270d51f7d5413a4b24fedf95523ff

Called when underlying graphics resources, such as textures, are lost.

This indicates that :sip:ref:`~PyQt6.QtCanvasPainter.QCanvasImage` objects returned from addImage() are no longer valid, and addImage() needs to be called again. If the :sip:ref:`~PyQt6.QtCanvasPainter.QCanvasPainterWidget.paint` implementation is such that this does not matter, for example because images are not used, or addImage() is always called, then no action is necessary. Otherwise, it is recommended to toggle a flag, or similar, and act accordingly in the next invocation of :sip:ref:`~PyQt6.QtCanvasPainter.QCanvasPainterWidget.paint`.

The same applies to :sip:ref:`~PyQt6.QtCanvasPainter.QCanvasOffscreenCanvas` objects returned from :sip:ref:`~PyQt6.QtCanvasPainter.QCanvasPainter.createCanvas`. When this function is called, the next invocation of :sip:ref:`~PyQt6.QtCanvasPainter.QCanvasPainterWidget.paint` should create new canvases and redraw their contents.

Graphics resources can be lost, for example, when the widget is moved to a new top-level window, because that implies being associated with a new :sip:ref:`~PyQt6.QtGui.QRhi` instance.

.. seealso:: :sip:ref:`~PyQt6.QtWidgets.QRhiWidget.releaseResources`.
