.. sip:method-description::
    :status: todo
    :pysig: 506c5899d9cd0dd8e1dd3132a6459f77
    :realsig: () const
    :digest: 8be04edab6b951dd61a045202bfbdcba

Returns the render target object that must be used with :sip:ref:`~PyQt6.QtGui.QRhiCommandBuffer.beginPass` in reimplementations of :sip:ref:`~PyQt6.QtWidgets.QRhiWidget.render`.

Must only be called from :sip:ref:`~PyQt6.QtWidgets.QRhiWidget.initialize` and :sip:ref:`~PyQt6.QtWidgets.QRhiWidget.render`.

Available only when autoRenderTarget is ``true``. Otherwise the returned value is ``nullptr`` and it is up the reimplementation of :sip:ref:`~PyQt6.QtWidgets.QRhiWidget.initialize` to create and manage a depth-stencil buffer and a :sip:ref:`~PyQt6.QtGui.QRhiTextureRenderTarget`.

When creating :sip:ref:`~PyQt6.QtGui.QRhiGraphicsPipeline`, a :sip:ref:`~PyQt6.QtGui.QRhiRenderPassDescriptor` is needed. This can be queried from the returned :sip:ref:`~PyQt6.QtGui.QRhiTextureRenderTarget` by calling renderPassDescriptor().

.. seealso:: :sip:ref:`~PyQt6.QtWidgets.QRhiWidget.colorTexture`, :sip:ref:`~PyQt6.QtWidgets.QRhiWidget.depthStencilBuffer`.
