.. sip:method-description::
    :status: todo
    :pysig: 248dfa1fd98b4de55aa2b5af1b5bbe30
    :realsig: (qsizetype) const
    :digest: 6601f31f1148d518237bf781be0c4bad

Returns the position of the path at *index*. This means position where path command (\ :sip:ref:`~PyQt6.QtCanvasPainter.QCanvasPath.moveTo`, :sip:ref:`~PyQt6.QtCanvasPainter.QCanvasPath.lineTo`, :sip:ref:`~PyQt6.QtCanvasPainter.QCanvasPath.bezierCurveTo` etc.) is at *index*. The index need to be between ``0`` and :sip:ref:`~PyQt6.QtCanvasPainter.QCanvasPath.commandsSize` - 1. When the path is empty, returns (0.0, 0.0).
