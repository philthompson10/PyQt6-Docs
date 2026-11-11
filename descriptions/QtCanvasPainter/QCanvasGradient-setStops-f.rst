.. sip:method-description::
    :status: todo
    :pysig: 9820b79c99d8fce130ef08d2fe274d6b
    :realsig: (const QCanvasGradientStops&)
    :digest: 2882f2d87e1f00071ce7ee216acbe0f0

Replaces the current set of stop points with the given *stops*.

The rules for the stops list are following:

* The list should contain at least 2 stops.

* The positions of the stops must be in the range 0 to 1, and must be sorted with the lowest stops first.

* The first position must be at 0.0 and the last position at 1.0.

.. seealso:: :sip:ref:`~PyQt6.QtCanvasPainter.QCanvasGradient.setColorAt`, :sip:ref:`~PyQt6.QtCanvasPainter.QCanvasGradient.stops`.
