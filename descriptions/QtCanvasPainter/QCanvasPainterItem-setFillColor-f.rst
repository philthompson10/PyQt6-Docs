.. sip:method-description::
    :status: todo
    :pysig: 5237000fc3bc4f513a579caca380c129
    :realsig: (QColor)
    :digest: 5758b76adfa3bfbfe4a70377a6830eb5

Set the fill color to *color*. This color will be used to draw the background of the item. The default color is black.

**Note:** When setting the fill color to not fully opaque (alpha channel less than 255), remember to set also :sip:ref:`~PyQt6.QtQuick.QQuickRhiItem.alphaBlending` to ``true``.

.. seealso:: :sip:ref:`~PyQt6.QtCanvasPainter.QCanvasPainterItem.fillColor`, :sip:ref:`~PyQt6.QtQuick.QQuickRhiItem.alphaBlending`.
