.. sip:method-description::
    :status: todo
    :pysig: dd5e73b1d4a76ce0a0dfb868f41bd317
    :realsig: (QCanvasOffscreenCanvas&)
    :digest: bed484ff002b8a3687777d71348e673b

Destroys the resources backing *canvas*. *canvas* becomes a :sip:ref:`~PyQt6.QtCanvasPainter.QCanvasOffscreenCanvas.isNull` then.

The painter automatically does this upon its destruction. Therefore, calling this function is only necessary when releasing the associated resources is desired right away.
