.. sip:method-description::
    :status: todo
    :pysig: f512f527d7b73ac99b019902d108a646
    :realsig: (const QCanvasImage&)
    :digest: 25334b0d0b27c1abecbc9a9744084460

Releases the resources associated with *image* and removes the image from the painter.

**Note:** This does not need to be normally called, because resources such as textures are released in the painter destructor anyway. This function is useful when there is a need to reduce memory usage due to having a lot images, and some of them are not used anymore.

**Note:** Removed images can not be used in paint operations anymore.

**Note:** Resources such as the textures created with the underlying 3D API may not get released immediately. Such operations may get deferred to subsequent frames, typically when this :sip:ref:`~PyQt6.QtCanvasPainter.QCanvasPainter` begins painting again after the active set of draw calls has been submitted.

.. seealso:: :sip:ref:`~PyQt6.QtCanvasPainter.QCanvasPainter.addImage`.
