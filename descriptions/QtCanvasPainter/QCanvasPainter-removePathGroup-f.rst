.. sip:method-description::
    :status: todo
    :pysig: fa7153f7ed1cb6c0fcf2ffb2fac21748
    :realsig: (int)
    :digest: 98bc33c676012f03928fd7ddb355096f

Removes *pathGroup* from the painter cache. Calling :sip:ref:`~PyQt6.QtCanvasPainter.QCanvasPainter.fill` or :sip:ref:`~PyQt6.QtCanvasPainter.QCanvasPainter.stroke` for *pathGroup* after this, will regenerate the path into the group cache.

**Note:** This does not need to be normally called as paths are removed in the painter destructor. Only use this to reduce memory usage when *pathGroup* is not needed anymore or e.g. when the path has a lot less commands that it has had in the past and buffer size should be reduced.

.. seealso:: :sip:ref:`~PyQt6.QtCanvasPainter.QCanvasPainter.fill`, :sip:ref:`~PyQt6.QtCanvasPainter.QCanvasPainter.stroke`.
