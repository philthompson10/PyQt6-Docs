.. sip:class-description::
    :status: todo
    :brief: Specifies a scissor rectangle
    :digest: fdedffae98e8a124cf3e32a0943f604b

Specifies a scissor rectangle.

Used with :sip:ref:`~PyQt6.QtGui.QRhiCommandBuffer.setScissor`. Setting a scissor rectangle is only possible with a :sip:ref:`~PyQt6.QtGui.QRhiGraphicsPipeline` that has :sip:ref:`~PyQt6.QtGui.QRhiGraphicsPipeline.Flag.UsesScissor` set.

:sip:ref:`~PyQt6.QtGui.QRhi` assumes OpenGL-style scissor coordinates, meaning x and y are bottom-left. Negative width or height are not allowed. However, apart from that, the flexible OpenGL semantics apply: negative x and y, partially out of bounds rectangles, etc. will be handled gracefully, clamping as appropriate. Therefore, any rendering logic targeting OpenGL can feed scissor rectangles into :sip:ref:`~PyQt6.QtGui.QRhiScissor` as-is, without any adaptation.

**Note:** This is a RHI API with limited compatibility guarantees, see :sip:ref:`~PyQt6.QtGui.QRhi` for details.

.. seealso:: :sip:ref:`~PyQt6.QtGui.QRhiCommandBuffer.setScissor`, :sip:ref:`~PyQt6.QtGui.QRhiViewport`.
