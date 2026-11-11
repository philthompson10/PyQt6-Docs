.. sip:method-description::
    :status: todo
    :pysig: 7541b8c73738befc3a04ee5874675861
    :realsig: () const
    :digest: 9c14eeefe80baa7e2143205fcd368cb4

Returns the depth-stencil buffer used by the widget's rendering.

Must only be called from :sip:ref:`~PyQt6.QtWidgets.QRhiWidget.initialize` and :sip:ref:`~PyQt6.QtWidgets.QRhiWidget.render`.

Available only when autoRenderTarget is ``true``. Otherwise the returned value is ``nullptr`` and it is up the reimplementation of :sip:ref:`~PyQt6.QtWidgets.QRhiWidget.initialize` to create and manage a depth-stencil buffer and a :sip:ref:`~PyQt6.QtGui.QRhiTextureRenderTarget`.

.. seealso:: :sip:ref:`~PyQt6.QtWidgets.QRhiWidget.colorTexture`, :sip:ref:`~PyQt6.QtWidgets.QRhiWidget.renderTarget`.
