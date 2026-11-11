.. sip:method-description::
    :status: todo
    :pysig: c506ff134babdd6e68ab3e6350e95305
    :realsig: (bool)
    :digest: da56e813dbdb36693a1ec405a475d8bb

Disable painter sharing if *enable* is ``false``.

Painter sharing is enabled by default.

When painter sharing is enabled, all painter items inside the same :sip:ref:`~PyQt6.QtQuick.QQuickWindow` will use the same :sip:ref:`~PyQt6.QtCanvasPainter.QCanvasPainter`.

If disabling painter sharing is desired, this function must be called early enough, for example from the derived class' constructor. Changing it afterwards, when the item has already initialized for painting, will have no effect.

If two items use dedicated, non-shared painters, each other's graphics resources, such as the ones backing :sip:ref:`~PyQt6.QtCanvasPainter.QCanvasImage` or QOffscreenCanvas, will not be visible to them. Whereas if the items are in the same window, and sharing is enabled, they can use images or canvases created by the other item, because they both use the same :sip:ref:`~PyQt6.QtCanvasPainter.QCanvasPainter`.

**Note:** Even when *enable* is true, painters are not shared between items belonging to different :sip:ref:`~PyQt6.QtQuick.QQuickWindow` instances, and by extension, to different scene graphs.

.. seealso:: :sip:ref:`~PyQt6.QtCanvasPainter.QCanvasPainterItemRenderer.hasSharedPainter`.
