.. sip:class-description::
    :status: todo
    :brief: Handles all painting for a QCanvasPainterItem
    :digest: 6b6b1b56f88affdd7ca07eacb3fd5805

The :sip:ref:`~PyQt6.QtCanvasPainter.QCanvasPainterItemRenderer` handles all painting for a :sip:ref:`~PyQt6.QtCanvasPainter.QCanvasPainterItem`.

Implement the :sip:ref:`~PyQt6.QtCanvasPainter.QCanvasPainterItemRenderer.paint` method to perform the rendering.

To expose data from the item to the renderer in a thread-safe manner, implement :sip:ref:`~PyQt6.QtCanvasPainter.QCanvasPainterItemRenderer.synchronizeData`.

The renderer object lives and operates on the `Qt Quick scene graph render thread <https://doc.qt.io/qt-6/qtquick-visualcanvas-scenegraph.html#scene-graph-and-rendering>`_, if there is one, since that is the thread on which :sip:ref:`~PyQt6.QtCanvasPainter.QCanvasPainterItem.createItemRenderer` and all the functions in this class are invoked.

If the :sip:ref:`~PyQt6.QtCanvasPainter.QCanvasPainterItem` is moved to a different :sip:ref:`~PyQt6.QtQuick.QQuickWindow`, it will get associated with a new :sip:ref:`~PyQt6.QtGui.QRhi`. Therefore, the renderer object is automatically destroyed, and a new one is created by invoking :sip:ref:`~PyQt6.QtCanvasPainter.QCanvasPainterItem.createItemRenderer` again. This allows simple management of :sip:ref:`~PyQt6.QtCanvasPainter.QCanvasImage` and :sip:ref:`~PyQt6.QtCanvasPainter.QCanvasOffscreenCanvas` objects, because they can be member variables in renderer, set up either in :sip:ref:`~PyQt6.QtCanvasPainter.QCanvasPainterItemRenderer.initializeResources` or in :sip:ref:`~PyQt6.QtCanvasPainter.QCanvasPainterItemRenderer.paint`, without having to reset them when the graphics resources are lost due to the window and :sip:ref:`~PyQt6.QtGui.QRhi` change, since it all happens implicitly by the destruction of the whole renderer object.

The below code snippet shows the typical structure of a :sip:ref:`~PyQt6.QtCanvasPainter.QCanvasPainterItemRenderer` subclass. See :sip:ref:`~PyQt6.QtCanvasPainter.QCanvasPainterItem` for an example of the ``MyItem`` class.

.. literalinclude:: ../../../snippets/qtcanvaspainter-src-canvaspainter-doc-snippets-renderer-ex-1.py

.. seealso:: :sip:ref:`~PyQt6.QtCanvasPainter.QCanvasPainterItem`.
