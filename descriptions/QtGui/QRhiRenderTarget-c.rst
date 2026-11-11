.. sip:class-description::
    :status: todo
    :brief: Represents an onscreen (swapchain) or offscreen (texture) render target
    :digest: 4e66ab1dd4958548525e6074cbaba8cd

Represents an onscreen (swapchain) or offscreen (texture) render target.

Applications do not create an instance of this class directly. Rather, it is the subclass :sip:ref:`~PyQt6.QtGui.QRhiTextureRenderTarget` that is instantiable by clients of the API via :sip:ref:`~PyQt6.QtGui.QRhi.newTextureRenderTarget`. The other subclass is :sip:ref:`~PyQt6.QtGui.QRhiSwapChainRenderTarget`, which is the type :sip:ref:`~PyQt6.QtGui.QRhiSwapChain` returns when calling :sip:ref:`~PyQt6.QtGui.QRhiSwapChain.currentFrameRenderTarget`.

**Note:** This is a RHI API with limited compatibility guarantees, see :sip:ref:`~PyQt6.QtGui.QRhi` for details.

.. seealso:: :sip:ref:`~PyQt6.QtGui.QRhiSwapChainRenderTarget`, :sip:ref:`~PyQt6.QtGui.QRhiTextureRenderTarget`.
