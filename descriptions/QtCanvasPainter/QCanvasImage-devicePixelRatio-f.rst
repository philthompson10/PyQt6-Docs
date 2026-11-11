.. sip:method-description::
    :status: todo
    :pysig: 546ade640b6edfbc8a086ef31347e768
    :realsig: () const
    :digest: e7d6af686c28a362615af103f5ae44ba

Returns the device pixel ratio for the image. This is the ratio between *device pixels* and *device independent pixels*.

A :sip:ref:`~PyQt6.QtCanvasPainter.QCanvasImage` with a greater than 1 device pixel ratio applies that scale factor when using the image. For example, ``drawImage(image, 0, 0)`` is then equivalent to ``drawImage(image, 0, 0, image.width() / image.devicePixelRatio(), image.height() / image.devicePixelRatio())``.

The default value is 1.0.

The value is carried over from the :sip:ref:`~PyQt6.QtGui.QImage` the :sip:ref:`~PyQt6.QtCanvasPainter.QCanvasImage` is created from. A :sip:ref:`~PyQt6.QtCanvasPainter.QCanvasImage` created from a texture or :sip:ref:`~PyQt6.QtCanvasPainter.QCanvasOffscreenCanvas` always has a device pixel ratio of 1.

.. seealso:: :sip:ref:`~PyQt6.QtGui.QImage`.
