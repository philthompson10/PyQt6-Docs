.. sip:method-description::
    :status: todo
    :pysig: b53df27f41e7e1e87eded6e72ecfdeb9
    :realsig: (const QPainterPath&)
    :digest: 75e17f1a0be68f7ee78022f4e9a5f940

Adds *path* into the current path.

**Note:** :sip:ref:`~PyQt6.QtCanvasPainter.QCanvasPainter` uses :sip:ref:`~PyQt6.QtCanvasPainter.QCanvasPainter.FillRule.NonZero` (\ :sip:ref:`~PyQt6.QtCore.Qt.FillRule.WindingFill`) fillrule by default, while :sip:ref:`~PyQt6.QtGui.QPainterPath` defaults to :sip:ref:`~PyQt6.QtCore.Qt.FillRule.OddEvenFill`. So remember to switch the fillRule if needed, for example, by using :sip:ref:`~PyQt6.QtCanvasPainter.QCanvasPainter.setFillRule`.

**Note:** This method is available mostly for the compatibility with :sip:ref:`~PyQt6.QtGui.QPainter` and :sip:ref:`~PyQt6.QtGui.QPainterPath`. It does not increase performance compared to painting the path directly with :sip:ref:`~PyQt6.QtCanvasPainter.QCanvasPainter` methods.
