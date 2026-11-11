.. sip:class-description::
    :status: todo
    :brief: Way to use the Qt Canvas Painter API in the QML Scene Graph
    :digest: 9fa618528ece39b380068b0db03ff3bb

The :sip:ref:`~PyQt6.QtCanvasPainter.QCanvasPainterItem` class provides a way to use the Qt Canvas Painter API in the QML Scene Graph.

To write your own painted item, you first create a subclass of :sip:ref:`~PyQt6.QtCanvasPainter.QCanvasPainterItem`, and then start by implementing its only pure virtual public function: :sip:ref:`~PyQt6.QtCanvasPainter.QCanvasPainterItem.createItemRenderer`, which returns an object that performs the actual painting.

The below code snippet shows the typical structure of a :sip:ref:`~PyQt6.QtCanvasPainter.QCanvasPainterItem` subclass. See :sip:ref:`~PyQt6.QtCanvasPainter.QCanvasPainterItemRenderer` for an example of the ``MyRenderer`` class.

.. literalinclude:: ../../../snippets/qtcanvaspainter-src-canvaspainter-doc-snippets-item-ex-1.py

Using the `QtQuick::Item::antialiasing <https://doc.qt.io/qt-6/qml-qtquick-item.html#antialiasing-prop>`_ property, it is possible to disable antialiasing. The default value is ``true``. When this is set to ``false``, it disables antialiasing even if the painting code calls :sip:ref:`~PyQt6.QtCanvasPainter.QCanvasPainter.setAntialias` with a value bigger than ``0``. Disabling antialiasing potentially increases the performance.

.. seealso:: :sip:ref:`~PyQt6.QtCanvasPainter.QCanvasPainterItemRenderer`.
