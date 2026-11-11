.. sip:method-description::
    :status: todo
    :pysig: 904ed7b0e5f600ef9a41b24df9fea808
    :realsig: (const QRectF&,qreal)
    :digest: ca81031993155d10fde915c0ebb7913f

Creates a move to that lies on the arc that occupies the given *rectangle* at *angle*.

Angles are specified in degrees. Clockwise arcs can be specified using negative angles. If *rectangle* is not square, *angle* is an eccentric angle and does not measure the direction from the center of the rectangle, as described in Arcs and Ellipses.

.. seealso:: :sip:ref:`~PyQt6.QtGui.QPainterPath.moveTo`, :sip:ref:`~PyQt6.QtGui.QPainterPath.arcTo`, Arcs and Ellipses.
