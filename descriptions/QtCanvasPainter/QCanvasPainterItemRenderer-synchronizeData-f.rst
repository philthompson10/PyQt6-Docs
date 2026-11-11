.. sip:method-description::
    :status: todo
    :pysig: 054941855379a3b9ca3ff51ac804f754
    :realsig: (QCanvasPainterItem*)
    :digest: 4069361cb4ebc2d3bb6dabba8c1e668e

Reimplement this method to synchronize data between *item* and item painter instances. This will be called before :sip:ref:`~PyQt6.QtCanvasPainter.QCanvasPainterItemRenderer.paint` each time item needs to be repainted.

This method is the only place where it is safe for the painter and the item to read and write each others variables.

Usually you should static_cast *item* to your real item type, and then exchange the data.
