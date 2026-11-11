.. sip:method-description::
    :status: todo
    :pysig: e977319e0a3045bbe1ad2e3bedbc857a
    :realsig: () const
    :digest: 6dddf84d524e327cfca6c7316eaae1db

Returns the texture serving as the color buffer for the widget.

Must only be called from :sip:ref:`~PyQt6.QtWidgets.QRhiWidget.initialize` and :sip:ref:`~PyQt6.QtWidgets.QRhiWidget.render`.

Unlike the depth-stencil buffer and the :sip:ref:`~PyQt6.QtGui.QRhiRenderTarget`, this texture is always available and is managed by the :sip:ref:`~PyQt6.QtWidgets.QRhiWidget`, independent of the value of autoRenderTarget.

**Note:** When :sip:ref:`~PyQt6.QtWidgets.QRhiWidget.sampleCount` is larger than 1, and so multisample antialiasing is enabled, the return value is ``nullptr``. Instead, query the :sip:ref:`~PyQt6.QtGui.QRhiRenderBuffer` by calling :sip:ref:`~PyQt6.QtWidgets.QRhiWidget.msaaColorBuffer`.

**Note:** The backing texture size and sample count can also be queried via the :sip:ref:`~PyQt6.QtGui.QRhiRenderTarget` returned from :sip:ref:`~PyQt6.QtWidgets.QRhiWidget.renderTarget`. This can be more convenient and compact than querying from the :sip:ref:`~PyQt6.QtGui.QRhiTexture` or :sip:ref:`~PyQt6.QtGui.QRhiRenderBuffer`, because it works regardless of multisampling is in use or not.

.. seealso:: :sip:ref:`~PyQt6.QtWidgets.QRhiWidget.msaaColorBuffer`, :sip:ref:`~PyQt6.QtWidgets.QRhiWidget.depthStencilBuffer`, :sip:ref:`~PyQt6.QtWidgets.QRhiWidget.renderTarget`, :sip:ref:`~PyQt6.QtWidgets.QRhiWidget.resolveTexture`.
