.. sip:method-description::
    :status: todo
    :pysig: 7541b8c73738befc3a04ee5874675861
    :realsig: () const
    :digest: a025ae6dacc5d75818f39b797409aa9a

Returns the depth-stencil buffer used by the item's rendering.

Must only be called from :sip:ref:`~PyQt6.QtQuick.QQuickRhiItemRenderer.initialize` and :sip:ref:`~PyQt6.QtQuick.QQuickRhiItemRenderer.render`.

Available only when :sip:ref:`~PyQt6.QtQuick.QQuickRhiItem.isAutoRenderTargetEnabled` is ``true``. Otherwise the returned value is ``nullptr`` and it is up the reimplementation of :sip:ref:`~PyQt6.QtQuick.QQuickRhiItemRenderer.initialize` to create and manage a depth-stencil buffer and a :sip:ref:`~PyQt6.QtGui.QRhiTextureRenderTarget`.

.. seealso:: :sip:ref:`~PyQt6.QtQuick.QQuickRhiItemRenderer.colorTexture`, :sip:ref:`~PyQt6.QtQuick.QQuickRhiItemRenderer.renderTarget`.
