.. sip:method-description::
    :status: todo
    :pysig: c506ff134babdd6e68ab3e6350e95305
    :realsig: (bool)
    :digest: 5906909ef00b7abb593568b6c28a1829

Disable painter sharing if *enable* is ``false``.

If painter sharing is enabled, all :sip:ref:`~PyQt6.QtCanvasPainter.QCanvasPainterWidget` instances inside the same :sip:ref:`~PyQt6.QtGui.QWindow` will use the same :sip:ref:`~PyQt6.QtCanvasPainter.QCanvasPainter`. This function must be early, e.g. from the derived class' constructor, and must not be changed afterwards.

Painter sharing is enabled by default.

If two widgets use dedicated, non-shared painters, each other's graphics resources, such as the ones backing :sip:ref:`~PyQt6.QtCanvasPainter.QCanvasImage` or QOffscreenCanvas, will not be visible to them. Whereas if the widgets are in the same window, and sharing is enabled, they can use images or canvases created by the other widget, because they both use the same :sip:ref:`~PyQt6.QtCanvasPainter.QCanvasPainter`.

**Note:** Even when *enable* is true, painters are not shared between widgets belonging to different windows (top-level widgets).

.. seealso:: :sip:ref:`~PyQt6.QtCanvasPainter.QCanvasPainterWidget.hasSharedPainter`.
