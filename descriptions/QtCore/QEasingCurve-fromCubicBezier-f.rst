.. sip:method-description::
    :status: todo
    :pysig: ccaf5eea594d2af4f7665b108bb40b32
    :realsig: (QPointF, QPointF)
    :digest: 34b449a5ef3a3ef2fcc4706614ca552f

Returns a cubic Bezier curve with the specified *c1* and *c2* control points.

A cubic Bezier curve is defined by four control points: C0, C1, C2, and C3. C0 and C3 correspond to the start and the end position, respectively. This function returns a cubic Bezier curve whose start point C0 is fixed at (0, 0) and the end point C3 is fixed at (1, 1).

This is a convenience helper, it is equivalent to calling *\ :sip:ref:`~PyQt6.QtCore.QEasingCurve.addCubicBezierSegment`\ (c1, c2, :sip:ref:`~PyQt6.QtCore.QPointF`\ (1, 1))*. If you need to construct a more complex cubic Bezier spline, use the :sip:ref:`~PyQt6.QtCore.QEasingCurve.addCubicBezierSegment` function instead.

.. seealso:: :sip:ref:`~PyQt6.QtCore.QEasingCurve.addCubicBezierSegment`.
