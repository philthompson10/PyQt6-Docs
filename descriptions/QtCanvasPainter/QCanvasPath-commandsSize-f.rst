.. sip:method-description::
    :status: todo
    :pysig: fa7153f7ed1cb6c0fcf2ffb2fac21748
    :realsig: () const
    :digest: 4e412a7f8ba79d3bf26b573edff99626

Returns the amount of commands in the path.

**Note:** Some path elements require several commands. For example :sip:ref:`~PyQt6.QtCanvasPainter.QCanvasPath.moveTo` and :sip:ref:`~PyQt6.QtCanvasPainter.QCanvasPath.lineTo` require ``1`` command, :sip:ref:`~PyQt6.QtCanvasPainter.QCanvasPath.bezierCurveTo` requires ``6`` commands and :sip:ref:`~PyQt6.QtCanvasPainter.QCanvasPath.roundRect` ``10`` commands.
