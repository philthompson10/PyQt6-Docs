.. sip:method-description::
    :status: todo
    :pysig: 13589a9b9c4c6c30ca426ce536937662
    :realsig: (const QRectF&)
    :digest: 3651d98249c288b8226a18f29a741dd1

Creates an ellipse within the specified *boundingRectangle* and adds it to the painter path as a closed subpath.

The ellipse is composed of a clockwise curve, starting and finishing at zero degrees (the 3 o'clock position). The curve is a cubic Bezier approximation of the ellipse, not an exact representation of it, as described in Arcs and Ellipses.

+-------------------------------------+---------------------------------------------------------------------------------------------------------+
| |image-qpainterpath-addellipse-png| | .. literalinclude:: ../../../snippets/qtbase-src-gui-doc-snippets-code-src_gui_painting_qpainterpath.py |
|                                     |     :lines: 178-188                                                                                     |
+-------------------------------------+---------------------------------------------------------------------------------------------------------+

.. seealso:: :sip:ref:`~PyQt6.QtGui.QPainterPath.arcTo`, :sip:ref:`~PyQt6.QtGui.QPainter.drawEllipse`, Composing a QPainterPath.

.. |image-qpainterpath-addellipse-png| image:: ../../../images/qpainterpath-addellipse.png
