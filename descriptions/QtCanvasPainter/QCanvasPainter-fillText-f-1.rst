.. sip:method-description::
    :status: todo
    :pysig: 614af502c63a6fe119d0f1b454badda8
    :realsig: (const QString&, QPointF, qreal)
    :digest: bc7768bf65a8cc7b923c05829a871412

Draws *text* string at the specified *point*, with current textAlign and textBaseline. To make the text wrap into multiple lines, set the text wrap mode using :sip:ref:`~PyQt6.QtCanvasPainter.QCanvasPainter.setTextWrapMode` to something else than the default ``NoWrap``. Optional *maxWidth* parameter defaults to ``0``. Meaning that when e.g. ``WordWrap`` has been set, text is wrapped on every word. Set the *maxWidth* parameter to preferred row width in pixels.

This is an overloaded method using :sip:ref:`~PyQt6.QtCore.QPointF`.

.. seealso:: :sip:ref:`~PyQt6.QtCanvasPainter.QCanvasPainter.setTextAlign`, :sip:ref:`~PyQt6.QtCanvasPainter.QCanvasPainter.setTextBaseline`, :sip:ref:`~PyQt6.QtCanvasPainter.QCanvasPainter.setTextWrapMode`.
