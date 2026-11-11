.. sip:method-description::
    :status: todo
    :pysig: 4ade4899404be507a256ebf0d30f5b88
    :realsig: (QRhiTexture*, QCanvasPainter::ImageFlags)
    :digest: 41a98341af9010f5d99307f891c60b21

Adds *texture* with *flags* available for the painter as a texture. The returned :sip:ref:`~PyQt6.QtCanvasPainter.QCanvasImage` can be used with :sip:ref:`~PyQt6.QtCanvasPainter.QCanvasPainter.drawImage` and :sip:ref:`~PyQt6.QtCanvasPainter.QCanvasImagePattern`.

**Note:** The ownership of *texture* is **not** taken.

.. seealso:: :sip:ref:`~PyQt6.QtCanvasPainter.QCanvasPainter.drawImage`, :sip:ref:`~PyQt6.QtCanvasPainter.QCanvasPainter.removeImage`.
