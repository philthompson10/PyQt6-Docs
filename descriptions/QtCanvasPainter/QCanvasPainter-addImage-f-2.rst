.. sip:method-description::
    :status: todo
    :pysig: e4efcfd586d06b706458db0e3c8db116
    :realsig: (const QCanvasOffscreenCanvas&, QCanvasPainter::ImageFlags)
    :digest: a304d9c70255df399c3c4e2ecff0578e

Registers *canvas* with *flags* to the painter so that it is available as an image. The returned :sip:ref:`~PyQt6.QtCanvasPainter.QCanvasImage` can be used with :sip:ref:`~PyQt6.QtCanvasPainter.QCanvasPainter.drawImage` and :sip:ref:`~PyQt6.QtCanvasPainter.QCanvasImagePattern`.

**Note:** *canvas* continues to manage the underlying native graphics resources, meaning :sip:ref:`~PyQt6.QtCanvasPainter.QCanvasPainter.removeImage` does not render *canvas* invalid.

.. seealso:: :sip:ref:`~PyQt6.QtCanvasPainter.QCanvasPainter.drawImage`, :sip:ref:`~PyQt6.QtCanvasPainter.QCanvasPainter.removeImage`.
