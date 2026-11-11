.. sip:method-description::
    :status: todo
    :pysig: fa7153f7ed1cb6c0fcf2ffb2fac21748
    :realsig: () const
    :digest: 8f30b880f36ea1546573a5ae61730a06

Returns the amount of commands data in the path.

Commands data basically means the points required by the commands.

**Note:** Some path elements require several data points. For example :sip:ref:`~PyQt6.QtCanvasPainter.QCanvasPath.closePath` requires ``0``, :sip:ref:`~PyQt6.QtCanvasPainter.QCanvasPath.moveTo` and :sip:ref:`~PyQt6.QtCanvasPainter.QCanvasPath.lineTo` require ``2``, :sip:ref:`~PyQt6.QtCanvasPainter.QCanvasPath.bezierCurveTo` requires 6 and :sip:ref:`~PyQt6.QtCanvasPainter.QCanvasPath.roundRect` requires ``34`` data points.
