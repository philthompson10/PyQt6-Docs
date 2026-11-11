.. sip:method-description::
    :status: todo
    :pysig: 912b6e538da95bf511003fdcc51b2629
    :realsig: (const QString&, QPointF, qreal) const
    :digest: ebf021f3066097ef6ee95609a7e62e81

Measures bounding box of a *text* string at *point*.

To measure multi-line text, set the text wrap mode using :sip:ref:`~PyQt6.QtCanvasPainter.QCanvasPainter.setTextWrapMode` to something else than the default ``NoWrap``. Also set the optional *maxWidth* parameter to preferred row width in pixels.

Returns :sip:ref:`~PyQt6.QtCore.QRectF` with values [xmin, ymin, width, height]. Measured values are returned in local coordinate space.
