.. sip:method-description::
    :status: todo
    :pysig: 3465554a88c9f3336441cc762a92d046
    :realsig: (const QRectF&,int,int)
    :digest: fcdc5d2b9668d494f965a27639e162f2

Draws the arc defined by the given *rectangle*, *startAngle* and *spanAngle*.

The *startAngle* and *spanAngle* must be specified in 1/16th of a degree, i.e. a full circle equals 5760 (16 \* 360). Positive values for the angles mean counter-clockwise while negative values mean the clockwise direction. Zero degrees is at the 3 o'clock position. If *rectangle* is not square, the angles are eccentric angles and do not measure the direction from the center of the rectangle, as described in Arcs and Ellipses.

+--------------------------+-----------------------------------------------------------------------------------------------------+
| |image-qpainter-arc-png| | .. literalinclude:: ../../../snippets/qtbase-src-gui-doc-snippets-code-src_gui_painting_qpainter.py |
|                          |     :lines: 220-225                                                                                 |
+--------------------------+-----------------------------------------------------------------------------------------------------+

.. seealso:: :sip:ref:`~PyQt6.QtGui.QPainter.drawPie`, :sip:ref:`~PyQt6.QtGui.QPainter.drawChord`, `Coordinate System <https://doc.qt.io/qt-6/coordsys.html>`_.

.. |image-qpainter-arc-png| image:: ../../../images/qpainter-arc.png
