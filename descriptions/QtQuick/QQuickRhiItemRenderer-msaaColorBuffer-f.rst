.. sip:method-description::
    :status: todo
    :pysig: 7541b8c73738befc3a04ee5874675861
    :realsig: () const
    :digest: b13075852f646e81cf1a2942b4e7a423

Returns the renderbuffer serving as the multisample color buffer for the item.

Must only be called from :sip:ref:`~PyQt6.QtQuick.QQuickRhiItemRenderer.initialize` and :sip:ref:`~PyQt6.QtQuick.QQuickRhiItemRenderer.render`.

When :sip:ref:`~PyQt6.QtQuick.QQuickRhiItem.sampleCount` is larger than 1, and so multisample antialising is enabled, the returned :sip:ref:`~PyQt6.QtGui.QRhiRenderBuffer` has a matching sample count and serves as the color buffer. Graphics pipelines used to render into this buffer must be created with the same sample count, and the depth-stencil buffer's sample count must match as well. The multisample content is expected to be resolved into the texture returned from :sip:ref:`~PyQt6.QtQuick.QQuickRhiItemRenderer.resolveTexture`. When :sip:ref:`~PyQt6.QtQuick.QQuickRhiItem.isAutoRenderTargetEnabled` is ``true``, :sip:ref:`~PyQt6.QtQuick.QQuickRhiItemRenderer.renderTarget` is set up automatically to do this, by setting up msaaColorBuffer() as the renderbuffer of color attachment 0 and :sip:ref:`~PyQt6.QtQuick.QQuickRhiItemRenderer.resolveTexture` as its resolveTexture.

When MSAA is not in use, the return value is ``nullptr``. Use :sip:ref:`~PyQt6.QtQuick.QQuickRhiItemRenderer.colorTexture` instead then.

Depending on the underlying 3D graphics API, there may be no practical difference between multisample textures and color renderbuffers with a sample count larger than 1 (\ :sip:ref:`~PyQt6.QtGui.QRhi` may just map both to the same native resource type). Some older APIs however may differentiate between textures and renderbuffers. In order to support OpenGL ES 3.0, where multisample renderbuffers are available, but multisample textures are not, :sip:ref:`~PyQt6.QtQuick.QQuickRhiItem` always performs MSAA by using a multisample :sip:ref:`~PyQt6.QtGui.QRhiRenderBuffer` as the color attachment (and never a multisample :sip:ref:`~PyQt6.QtGui.QRhiTexture`).

**Note:** The backing texture size and sample count can also be queried via the :sip:ref:`~PyQt6.QtGui.QRhiRenderTarget` returned from :sip:ref:`~PyQt6.QtQuick.QQuickRhiItemRenderer.renderTarget`. This can be more convenient and compact than querying from the :sip:ref:`~PyQt6.QtGui.QRhiTexture` or :sip:ref:`~PyQt6.QtGui.QRhiRenderBuffer`, because it works regardless of multisampling is in use or not.

.. seealso:: :sip:ref:`~PyQt6.QtQuick.QQuickRhiItemRenderer.colorTexture`, :sip:ref:`~PyQt6.QtQuick.QQuickRhiItemRenderer.depthStencilBuffer`, :sip:ref:`~PyQt6.QtQuick.QQuickRhiItemRenderer.renderTarget`, :sip:ref:`~PyQt6.QtQuick.QQuickRhiItemRenderer.resolveTexture`.
