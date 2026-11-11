.. sip:method-description::
    :status: todo
    :pysig: 18fc5c924ded5804300a9bbe6932ebba
    :realsig: (QCanvasPainter*)
    :digest: 47cc0ab71197c8eaae44360c73d1817c

Reimplement this method to initialize resources using *painter*. This will be called once **before** the first :sip:ref:`~PyQt6.QtCanvasPainter.QCanvasPainterItemRenderer.synchronizeData`.

**Note:** This function is not called when the size of the :sip:ref:`~PyQt6.QtCanvasPainter.QCanvasPainterItem` changes.

.. seealso:: :sip:ref:`~PyQt6.QtCanvasPainter.QCanvasPainter.addImage`, :sip:ref:`~PyQt6.QtCanvasPainter.QCanvasPainter.createCanvas`.
