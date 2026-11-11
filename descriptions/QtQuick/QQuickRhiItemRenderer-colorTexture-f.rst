.. sip:method-description::
    :status: todo
    :pysig: e977319e0a3045bbe1ad2e3bedbc857a
    :realsig: () const
    :digest: 3c9f868d016e4fa9353f429776c2fda1

Returns the texture serving as the color buffer for the item.

Must only be called from :sip:ref:`~PyQt6.QtQuick.QQuickRhiItemRenderer.initialize` and :sip:ref:`~PyQt6.QtQuick.QQuickRhiItemRenderer.render`.

Unlike the depth-stencil buffer and the :sip:ref:`~PyQt6.QtGui.QRhiRenderTarget`, this texture is always available and is managed by the :sip:ref:`~PyQt6.QtQuick.QQuickRhiItem`, independent of the value of :sip:ref:`~PyQt6.QtQuick.QQuickRhiItem.isAutoRenderTargetEnabled`.

**Note:** When :sip:ref:`~PyQt6.QtQuick.QQuickRhiItem.sampleCount` is larger than 1, and so multisample antialiasing is enabled, the return value is ``nullptr``. Instead, query the :sip:ref:`~PyQt6.QtGui.QRhiRenderBuffer` by calling :sip:ref:`~PyQt6.QtQuick.QQuickRhiItemRenderer.msaaColorBuffer`.

**Note:** The backing texture size and sample count can also be queried via the :sip:ref:`~PyQt6.QtGui.QRhiRenderTarget` returned from :sip:ref:`~PyQt6.QtQuick.QQuickRhiItemRenderer.renderTarget`. This can be more convenient and compact than querying from the :sip:ref:`~PyQt6.QtGui.QRhiTexture` or :sip:ref:`~PyQt6.QtGui.QRhiRenderBuffer`, because it works regardless of multisampling is in use or not.

.. seealso:: :sip:ref:`~PyQt6.QtQuick.QQuickRhiItemRenderer.msaaColorBuffer`, :sip:ref:`~PyQt6.QtQuick.QQuickRhiItemRenderer.depthStencilBuffer`, :sip:ref:`~PyQt6.QtQuick.QQuickRhiItemRenderer.renderTarget`, :sip:ref:`~PyQt6.QtQuick.QQuickRhiItemRenderer.resolveTexture`.
