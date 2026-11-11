.. sip:method-description::
    :status: todo
    :pysig: 675c4919eb84ce9069752c2282e24d44
    :realsig: (const QImage&, QCanvasPainter::ImageFlags)
    :digest: 1a9f1efcfeb095886e554b7d68565fac

Adds *image* with *flags* available for the painter as a texture. Returns :sip:ref:`~PyQt6.QtCanvasPainter.QCanvasImage` with the texture id and other information about the image. Returned :sip:ref:`~PyQt6.QtCanvasPainter.QCanvasImage` can then be used with :sip:ref:`~PyQt6.QtCanvasPainter.QCanvasPainter.drawImage` and :sip:ref:`~PyQt6.QtCanvasPainter.QCanvasImagePattern`. After calling this method, the *image* :sip:ref:`~PyQt6.QtGui.QImage` does not need to be kept in memory.

Calling with the same *image* is a cheap operation, since a cache hit is expected.

Care must be taken when optimizing to call addImage() only once. That is not always sufficient, depending on the application design. For example, if the underlying graphics resources are lost, e.g. because the painter is associated with a new :sip:ref:`~PyQt6.QtGui.QRhi` under the hood due to moving a widget to a new top-level, then calling this function is essential in order to re-create the native graphics textures from *image*.

.. seealso:: :sip:ref:`~PyQt6.QtCanvasPainter.QCanvasPainter.drawImage`, :sip:ref:`~PyQt6.QtCanvasPainter.QCanvasPainter.removeImage`.
