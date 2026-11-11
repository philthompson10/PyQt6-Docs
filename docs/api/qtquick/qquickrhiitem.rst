:orphan:

.. sip:class:: PyQt6.QtQuick.QQuickRhiItem
    :inherits: :sip:ref:`~PyQt6.QtQuick.QQuickItem`
    :description: QtQuick/QQuickRhiItem-c.rst

    .. sip:enum:: PyQt6.QtQuick.QQuickRhiItem.TextureFormat
        :description: QtQuick/QQuickRhiItem-TextureFormat-e.rst

        .. sip:enum-member:: PyQt6.QtQuick.QQuickRhiItem.TextureFormat.RGB10A2
            :description: QtQuick/QQuickRhiItem-TextureFormat-RGB10A2-v.rst

        .. sip:enum-member:: PyQt6.QtQuick.QQuickRhiItem.TextureFormat.RGBA16F
            :description: QtQuick/QQuickRhiItem-TextureFormat-RGBA16F-v.rst

        .. sip:enum-member:: PyQt6.QtQuick.QQuickRhiItem.TextureFormat.RGBA32F
            :description: QtQuick/QQuickRhiItem-TextureFormat-RGBA32F-v.rst

        .. sip:enum-member:: PyQt6.QtQuick.QQuickRhiItem.TextureFormat.RGBA8
            :description: QtQuick/QQuickRhiItem-TextureFormat-RGBA8-v.rst

    .. sip:method:: PyQt6.QtQuick.QQuickRhiItem.__init__
        :args:
            parent: :sip:ref:`~PyQt6.QtQuick.QQuickItem` = None
        :description: QtQuick/QQuickRhiItem-__init__-f.rst

    .. sip:method:: PyQt6.QtQuick.QQuickRhiItem.alphaBlending
        :returns:
            bool
        :description: QtQuick/QQuickRhiItem-alphaBlending-f.rst

    .. sip:method:: PyQt6.QtQuick.QQuickRhiItem.colorBufferFormat
        :returns:
            :sip:ref:`~PyQt6.QtQuick.QQuickRhiItem.TextureFormat`
        :description: QtQuick/QQuickRhiItem-colorBufferFormat-f.rst

    .. sip:method:: PyQt6.QtQuick.QQuickRhiItem.createRenderer
        :returns:
            :sip:ref:`~PyQt6.QtQuick.QQuickRhiItemRenderer`
        :description: QtQuick/QQuickRhiItem-createRenderer-f.rst

    .. sip:method:: PyQt6.QtQuick.QQuickRhiItem.effectiveColorBufferSize
        :returns:
            :sip:ref:`~PyQt6.QtCore.QSize`
        :description: QtQuick/QQuickRhiItem-effectiveColorBufferSize-f.rst

    .. sip:method:: PyQt6.QtQuick.QQuickRhiItem.event
        :args:
            :sip:ref:`~PyQt6.QtCore.QEvent`
        :returns:
            bool
        :description: QtQuick/QQuickRhiItem-event-f.rst

    .. sip:method:: PyQt6.QtQuick.QQuickRhiItem.fixedColorBufferHeight
        :returns:
            int
        :description: QtQuick/QQuickRhiItem-fixedColorBufferHeight-f.rst

    .. sip:method:: PyQt6.QtQuick.QQuickRhiItem.fixedColorBufferWidth
        :returns:
            int
        :description: QtQuick/QQuickRhiItem-fixedColorBufferWidth-f.rst

    .. sip:method:: PyQt6.QtQuick.QQuickRhiItem.geometryChange
        :args:
            :sip:ref:`~PyQt6.QtCore.QRectF`
            :sip:ref:`~PyQt6.QtCore.QRectF`
        :description: QtQuick/QQuickRhiItem-geometryChange-f.rst

    .. sip:method:: PyQt6.QtQuick.QQuickRhiItem.isAutoRenderTargetEnabled
        :returns:
            bool
        :description: QtQuick/QQuickRhiItem-isAutoRenderTargetEnabled-f.rst

    .. sip:method:: PyQt6.QtQuick.QQuickRhiItem.isMirrorVerticallyEnabled
        :returns:
            bool
        :description: QtQuick/QQuickRhiItem-isMirrorVerticallyEnabled-f.rst

    .. sip:method:: PyQt6.QtQuick.QQuickRhiItem.isTextureProvider
        :returns:
            bool
        :description: QtQuick/QQuickRhiItem-isTextureProvider-f.rst

    .. sip:method:: PyQt6.QtQuick.QQuickRhiItem.releaseResources
        :description: QtQuick/QQuickRhiItem-releaseResources-f.rst

    .. sip:method:: PyQt6.QtQuick.QQuickRhiItem.sampleCount
        :returns:
            int
        :description: QtQuick/QQuickRhiItem-sampleCount-f.rst

    .. sip:method:: PyQt6.QtQuick.QQuickRhiItem.setAlphaBlending
        :args:
            bool
        :description: QtQuick/QQuickRhiItem-setAlphaBlending-f.rst

    .. sip:method:: PyQt6.QtQuick.QQuickRhiItem.setAutoRenderTarget
        :args:
            bool
        :description: QtQuick/QQuickRhiItem-setAutoRenderTarget-f.rst

    .. sip:method:: PyQt6.QtQuick.QQuickRhiItem.setColorBufferFormat
        :args:
            :sip:ref:`~PyQt6.QtQuick.QQuickRhiItem.TextureFormat`
        :description: QtQuick/QQuickRhiItem-setColorBufferFormat-f.rst

    .. sip:method:: PyQt6.QtQuick.QQuickRhiItem.setFixedColorBufferHeight
        :args:
            int
        :description: QtQuick/QQuickRhiItem-setFixedColorBufferHeight-f.rst

    .. sip:method:: PyQt6.QtQuick.QQuickRhiItem.setFixedColorBufferWidth
        :args:
            int
        :description: QtQuick/QQuickRhiItem-setFixedColorBufferWidth-f.rst

    .. sip:method:: PyQt6.QtQuick.QQuickRhiItem.setMirrorVertically
        :args:
            bool
        :description: QtQuick/QQuickRhiItem-setMirrorVertically-f.rst

    .. sip:method:: PyQt6.QtQuick.QQuickRhiItem.setSampleCount
        :args:
            int
        :description: QtQuick/QQuickRhiItem-setSampleCount-f.rst

    .. sip:method:: PyQt6.QtQuick.QQuickRhiItem.textureProvider
        :returns:
            :sip:ref:`~PyQt6.QtQuick.QSGTextureProvider`
        :description: QtQuick/QQuickRhiItem-textureProvider-f.rst

    .. sip:method:: PyQt6.QtQuick.QQuickRhiItem.updatePaintNode
        :args:
            :sip:ref:`~PyQt6.QtQuick.QSGNode`
            :sip:ref:`~PyQt6.QtQuick.QQuickItem.UpdatePaintNodeData`
        :returns:
            :sip:ref:`~PyQt6.QtQuick.QSGNode`
        :description: QtQuick/QQuickRhiItem-updatePaintNode-f.rst

    .. sip:signal:: PyQt6.QtQuick.QQuickRhiItem.alphaBlendingChanged
        :description: QtQuick/QQuickRhiItem-alphaBlendingChanged-s.rst

    .. sip:signal:: PyQt6.QtQuick.QQuickRhiItem.colorBufferFormatChanged
        :description: QtQuick/QQuickRhiItem-colorBufferFormatChanged-s.rst

    .. sip:signal:: PyQt6.QtQuick.QQuickRhiItem.effectiveColorBufferSizeChanged
        :description: QtQuick/QQuickRhiItem-effectiveColorBufferSizeChanged-s.rst

    .. sip:signal:: PyQt6.QtQuick.QQuickRhiItem.fixedColorBufferHeightChanged
        :description: QtQuick/QQuickRhiItem-fixedColorBufferHeightChanged-s.rst

    .. sip:signal:: PyQt6.QtQuick.QQuickRhiItem.fixedColorBufferWidthChanged
        :description: QtQuick/QQuickRhiItem-fixedColorBufferWidthChanged-s.rst

    .. sip:signal:: PyQt6.QtQuick.QQuickRhiItem.mirrorVerticallyChanged
        :description: QtQuick/QQuickRhiItem-mirrorVerticallyChanged-s.rst

    .. sip:signal:: PyQt6.QtQuick.QQuickRhiItem.sampleCountChanged
        :description: QtQuick/QQuickRhiItem-sampleCountChanged-s.rst
