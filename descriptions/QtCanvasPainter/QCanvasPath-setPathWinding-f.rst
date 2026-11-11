.. sip:method-description::
    :status: todo
    :pysig: b672a6d2bcac3519b0a368f97b80ffd1
    :realsig: (QCanvasPainter::PathWinding)
    :digest: c1cad1ecc4fd6be60999a523389dda9f

Sets the current sub-path *winding* to either ``QCanvasPainter::CounterClockWise`` (default) or ``QCanvasPainter::ClockWise``. CounterClockWise draws solid subpaths while ClockWise draws holes.

**Note:** This is a command, similar to :sip:ref:`~PyQt6.QtCanvasPainter.QCanvasPath.lineTo`, :sip:ref:`~PyQt6.QtCanvasPainter.QCanvasPath.moveTo`, etc., and therefore setting the winding should be done before the rest of the commands to which the changed winding is meant to be applied to.
