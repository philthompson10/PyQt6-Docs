.. sip:method-description::
    :status: todo
    :pysig: e977319e0a3045bbe1ad2e3bedbc857a
    :realsig: () const
    :digest: 8e7aa34d8cea14157e615c5f7443296c

Returns the non-multisample texture to which the multisample content is resolved.

The result is ``nullptr`` when multisample antialiasing is not enabled.

Must only be called from :sip:ref:`~PyQt6.QtQuick.QQuickRhiItemRenderer.initialize` and :sip:ref:`~PyQt6.QtQuick.QQuickRhiItemRenderer.render`.

With MSAA enabled, this is the texture that gets used by the item's underlying scene graph node when texturing a quad in the main render pass of Qt Quick. However, the :sip:ref:`~PyQt6.QtQuick.QQuickRhiItemRenderer`'s rendering must target the (multisample) :sip:ref:`~PyQt6.QtGui.QRhiRenderBuffer` returned from :sip:ref:`~PyQt6.QtQuick.QQuickRhiItemRenderer.msaaColorBuffer`. When :sip:ref:`~PyQt6.QtQuick.QQuickRhiItem.isAutoRenderTargetEnabled` is ``true``, this is taken care of by the :sip:ref:`~PyQt6.QtGui.QRhiRenderTarget` returned from :sip:ref:`~PyQt6.QtQuick.QQuickRhiItemRenderer.renderTarget`. Otherwise, it is up to the subclass code to correctly configure a render target object with both the color buffer and resolve textures.

.. seealso:: :sip:ref:`~PyQt6.QtQuick.QQuickRhiItemRenderer.colorTexture`.
