.. sip:method-description::
    :status: todo
    :pysig: e977319e0a3045bbe1ad2e3bedbc857a
    :realsig: () const
    :digest: 504940226344fd1e73a1b57163feb0b3

Returns the non-multisample texture to which the multisample content is resolved.

The result is ``nullptr`` when multisample antialiasing is not enabled.

Must only be called from :sip:ref:`~PyQt6.QtWidgets.QRhiWidget.initialize` and :sip:ref:`~PyQt6.QtWidgets.QRhiWidget.render`.

With MSAA enabled, this is the texture that gets composited with the rest of the :sip:ref:`~PyQt6.QtWidgets.QWidget` content on-screen. However, the :sip:ref:`~PyQt6.QtWidgets.QRhiWidget`'s rendering must target the (multisample) :sip:ref:`~PyQt6.QtGui.QRhiRenderBuffer` returned from :sip:ref:`~PyQt6.QtWidgets.QRhiWidget.msaaColorBuffer`. When autoRenderTarget is ``true``, this is taken care of by the :sip:ref:`~PyQt6.QtGui.QRhiRenderTarget` returned from :sip:ref:`~PyQt6.QtWidgets.QRhiWidget.renderTarget`. Otherwise, it is up to the subclass code to correctly configure a render target object with both the color buffer and resolve textures.

.. seealso:: :sip:ref:`~PyQt6.QtWidgets.QRhiWidget.colorTexture`.
