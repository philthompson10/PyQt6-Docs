.. sip:method-description::
    :status: todo
    :pysig: 18fc5c924ded5804300a9bbe6932ebba
    :realsig: (QCanvasPainter*)
    :digest: 153db12d696b9c39bd88cef5c439f357

Reimplement this method to paint using *painter*.

This will get called after the item has been filled with :sip:ref:`~PyQt6.QtCanvasPainter.QCanvasPainterItemRenderer.fillColor`.

paint() is called from renderer thread. To access item data safely, copy it in :sip:ref:`~PyQt6.QtCanvasPainter.QCanvasPainterItemRenderer.synchronizeData`.

.. seealso:: :sip:ref:`~PyQt6.QtCanvasPainter.QCanvasPainterItemRenderer.synchronizeData`.
