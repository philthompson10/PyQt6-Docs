.. sip:method-description::
    :status: todo
    :pysig: 506c5899d9cd0dd8e1dd3132a6459f77
    :realsig: () const
    :digest: cbdf5a1888063dcfc8c18fc07f736409

Returns the render target object that must be used with :sip:ref:`~PyQt6.QtGui.QRhiCommandBuffer.beginPass` in reimplementations of :sip:ref:`~PyQt6.QtQuick.QQuickRhiItemRenderer.render`.

Must only be called from :sip:ref:`~PyQt6.QtQuick.QQuickRhiItemRenderer.initialize` and :sip:ref:`~PyQt6.QtQuick.QQuickRhiItemRenderer.render`.

Available only when :sip:ref:`~PyQt6.QtQuick.QQuickRhiItem.isAutoRenderTargetEnabled` is ``true``. Otherwise the returned value is ``nullptr`` and it is up the reimplementation of :sip:ref:`~PyQt6.QtQuick.QQuickRhiItemRenderer.initialize` to create and manage a depth-stencil buffer and a :sip:ref:`~PyQt6.QtGui.QRhiTextureRenderTarget`.

When creating :sip:ref:`~PyQt6.QtGui.QRhiGraphicsPipeline`, a :sip:ref:`~PyQt6.QtGui.QRhiRenderPassDescriptor` is needed. This can be queried from the returned :sip:ref:`~PyQt6.QtGui.QRhiTextureRenderTarget` by calling renderPassDescriptor().

**Note:** The returned :sip:ref:`~PyQt6.QtGui.QRhiTextureRenderTarget` always reports a devicePixelRatio() of ``1``. This is because only swapchains and the associated window have a concept of device pixel ratio, not textures, and the render target here always refers to a texture. If the on-screen scale factor is relevant for rendering, query and store it via the item's ``window()->effectiveDevicePixelRatio()`` in :sip:ref:`~PyQt6.QtQuick.QQuickRhiItemRenderer.synchronize`. When doing so, always prefer using :sip:ref:`~PyQt6.QtQuick.QQuickWindow.effectiveDevicePixelRatio` over the base class' :sip:ref:`~PyQt6.QtGui.QWindow.devicePixelRatio`.

.. seealso:: :sip:ref:`~PyQt6.QtQuick.QQuickRhiItemRenderer.colorTexture`, :sip:ref:`~PyQt6.QtQuick.QQuickRhiItemRenderer.depthStencilBuffer`, :sip:ref:`~PyQt6.QtQuick.QQuickWindow.effectiveDevicePixelRatio`.
