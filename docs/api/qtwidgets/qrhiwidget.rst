:orphan:

.. sip:class:: PyQt6.QtWidgets.QRhiWidget
    :inherits: :sip:ref:`~PyQt6.QtWidgets.QWidget`
    :description: QtWidgets/QRhiWidget-c.rst

    .. sip:enum:: PyQt6.QtWidgets.QRhiWidget.Api
        :description: QtWidgets/QRhiWidget-Api-e.rst

        .. sip:enum-member:: PyQt6.QtWidgets.QRhiWidget.Api.Direct3D11
            :description: QtWidgets/QRhiWidget-Api-Direct3D11-v.rst

        .. sip:enum-member:: PyQt6.QtWidgets.QRhiWidget.Api.Direct3D12
            :description: QtWidgets/QRhiWidget-Api-Direct3D12-v.rst

        .. sip:enum-member:: PyQt6.QtWidgets.QRhiWidget.Api.Metal
            :description: QtWidgets/QRhiWidget-Api-Metal-v.rst

        .. sip:enum-member:: PyQt6.QtWidgets.QRhiWidget.Api.Null
            :description: QtWidgets/QRhiWidget-Api-Null-v.rst

        .. sip:enum-member:: PyQt6.QtWidgets.QRhiWidget.Api.OpenGL
            :description: QtWidgets/QRhiWidget-Api-OpenGL-v.rst

        .. sip:enum-member:: PyQt6.QtWidgets.QRhiWidget.Api.Vulkan
            :description: QtWidgets/QRhiWidget-Api-Vulkan-v.rst

    .. sip:enum:: PyQt6.QtWidgets.QRhiWidget.TextureFormat
        :description: QtWidgets/QRhiWidget-TextureFormat-e.rst

        .. sip:enum-member:: PyQt6.QtWidgets.QRhiWidget.TextureFormat.RGB10A2
            :description: QtWidgets/QRhiWidget-TextureFormat-RGB10A2-v.rst

        .. sip:enum-member:: PyQt6.QtWidgets.QRhiWidget.TextureFormat.RGBA16F
            :description: QtWidgets/QRhiWidget-TextureFormat-RGBA16F-v.rst

        .. sip:enum-member:: PyQt6.QtWidgets.QRhiWidget.TextureFormat.RGBA32F
            :description: QtWidgets/QRhiWidget-TextureFormat-RGBA32F-v.rst

        .. sip:enum-member:: PyQt6.QtWidgets.QRhiWidget.TextureFormat.RGBA8
            :description: QtWidgets/QRhiWidget-TextureFormat-RGBA8-v.rst

    .. sip:method:: PyQt6.QtWidgets.QRhiWidget.__init__
        :args:
            parent: :sip:ref:`~PyQt6.QtWidgets.QWidget` = None
            flags: :sip:ref:`~PyQt6.QtCore.Qt.WindowType` = {}
        :description: QtWidgets/QRhiWidget-__init__-f.rst

    .. sip:method:: PyQt6.QtWidgets.QRhiWidget.api
        :returns:
            :sip:ref:`~PyQt6.QtWidgets.QRhiWidget.Api`
        :description: QtWidgets/QRhiWidget-api-f.rst

    .. sip:method:: PyQt6.QtWidgets.QRhiWidget.colorBufferFormat
        :returns:
            :sip:ref:`~PyQt6.QtWidgets.QRhiWidget.TextureFormat`
        :description: QtWidgets/QRhiWidget-colorBufferFormat-f.rst

    .. sip:method:: PyQt6.QtWidgets.QRhiWidget.colorTexture
        :returns:
            :sip:ref:`~PyQt6.QtGui.QRhiTexture`
        :description: QtWidgets/QRhiWidget-colorTexture-f.rst

    .. sip:method:: PyQt6.QtWidgets.QRhiWidget.depthStencilBuffer
        :returns:
            :sip:ref:`~PyQt6.QtGui.QRhiRenderBuffer`
        :description: QtWidgets/QRhiWidget-depthStencilBuffer-f.rst

    .. sip:method:: PyQt6.QtWidgets.QRhiWidget.event
        :args:
            :sip:ref:`~PyQt6.QtCore.QEvent`
        :returns:
            bool
        :description: QtWidgets/QRhiWidget-event-f.rst

    .. sip:method:: PyQt6.QtWidgets.QRhiWidget.fixedColorBufferSize
        :returns:
            :sip:ref:`~PyQt6.QtCore.QSize`
        :description: QtWidgets/QRhiWidget-fixedColorBufferSize-f.rst

    .. sip:method:: PyQt6.QtWidgets.QRhiWidget.grabFramebuffer
        :returns:
            :sip:ref:`~PyQt6.QtGui.QImage`
        :description: QtWidgets/QRhiWidget-grabFramebuffer-f.rst

    .. sip:method:: PyQt6.QtWidgets.QRhiWidget.initialize
        :args:
            :sip:ref:`~PyQt6.QtGui.QRhiCommandBuffer`
        :description: QtWidgets/QRhiWidget-initialize-f.rst

    .. sip:method:: PyQt6.QtWidgets.QRhiWidget.isDebugLayerEnabled
        :returns:
            bool
        :description: QtWidgets/QRhiWidget-isDebugLayerEnabled-f.rst

    .. sip:method:: PyQt6.QtWidgets.QRhiWidget.isMirrorVerticallyEnabled
        :returns:
            bool
        :description: QtWidgets/QRhiWidget-isMirrorVerticallyEnabled-f.rst

    .. sip:method:: PyQt6.QtWidgets.QRhiWidget.msaaColorBuffer
        :returns:
            :sip:ref:`~PyQt6.QtGui.QRhiRenderBuffer`
        :description: QtWidgets/QRhiWidget-msaaColorBuffer-f.rst

    .. sip:method:: PyQt6.QtWidgets.QRhiWidget.paintEvent
        :args:
            :sip:ref:`~PyQt6.QtGui.QPaintEvent`
        :description: QtWidgets/QRhiWidget-paintEvent-f.rst

    .. sip:method:: PyQt6.QtWidgets.QRhiWidget.releaseResources
        :description: QtWidgets/QRhiWidget-releaseResources-f.rst

    .. sip:method:: PyQt6.QtWidgets.QRhiWidget.render
        :args:
            :sip:ref:`~PyQt6.QtGui.QRhiCommandBuffer`
        :description: QtWidgets/QRhiWidget-render-f.rst

    .. sip:method:: PyQt6.QtWidgets.QRhiWidget.renderTarget
        :returns:
            :sip:ref:`~PyQt6.QtGui.QRhiRenderTarget`
        :description: QtWidgets/QRhiWidget-renderTarget-f.rst

    .. sip:method:: PyQt6.QtWidgets.QRhiWidget.resizeEvent
        :args:
            :sip:ref:`~PyQt6.QtGui.QResizeEvent`
        :description: QtWidgets/QRhiWidget-resizeEvent-f.rst

    .. sip:method:: PyQt6.QtWidgets.QRhiWidget.resolveTexture
        :returns:
            :sip:ref:`~PyQt6.QtGui.QRhiTexture`
        :description: QtWidgets/QRhiWidget-resolveTexture-f.rst

    .. sip:method:: PyQt6.QtWidgets.QRhiWidget.rhi
        :returns:
            :sip:ref:`~PyQt6.QtGui.QRhi`
        :description: QtWidgets/QRhiWidget-rhi-f.rst

    .. sip:method:: PyQt6.QtWidgets.QRhiWidget.sampleCount
        :returns:
            int
        :description: QtWidgets/QRhiWidget-sampleCount-f.rst

    .. sip:method:: PyQt6.QtWidgets.QRhiWidget.setApi
        :args:
            :sip:ref:`~PyQt6.QtWidgets.QRhiWidget.Api`
        :description: QtWidgets/QRhiWidget-setApi-f.rst

    .. sip:method:: PyQt6.QtWidgets.QRhiWidget.setAutoRenderTarget
        :args:
            bool
        :description: QtWidgets/QRhiWidget-setAutoRenderTarget-f.rst

    .. sip:method:: PyQt6.QtWidgets.QRhiWidget.setColorBufferFormat
        :args:
            :sip:ref:`~PyQt6.QtWidgets.QRhiWidget.TextureFormat`
        :description: QtWidgets/QRhiWidget-setColorBufferFormat-f.rst

    .. sip:method:: PyQt6.QtWidgets.QRhiWidget.setDebugLayerEnabled
        :args:
            bool
        :description: QtWidgets/QRhiWidget-setDebugLayerEnabled-f.rst

    .. sip:method:: PyQt6.QtWidgets.QRhiWidget.setFixedColorBufferSize
        :args:
            :sip:ref:`~PyQt6.QtCore.QSize`
        :description: QtWidgets/QRhiWidget-setFixedColorBufferSize-f.rst

    .. sip:method:: PyQt6.QtWidgets.QRhiWidget.setFixedColorBufferSize
        :args:
            int
            int
        :description: QtWidgets/QRhiWidget-setFixedColorBufferSize-f-1.rst

    .. sip:method:: PyQt6.QtWidgets.QRhiWidget.setMirrorVertically
        :args:
            bool
        :description: QtWidgets/QRhiWidget-setMirrorVertically-f.rst

    .. sip:method:: PyQt6.QtWidgets.QRhiWidget.setSampleCount
        :args:
            int
        :description: QtWidgets/QRhiWidget-setSampleCount-f.rst

    .. sip:signal:: PyQt6.QtWidgets.QRhiWidget.colorBufferFormatChanged
        :args:
            :sip:ref:`~PyQt6.QtWidgets.QRhiWidget.TextureFormat`
        :description: QtWidgets/QRhiWidget-colorBufferFormatChanged-s.rst

    .. sip:signal:: PyQt6.QtWidgets.QRhiWidget.fixedColorBufferSizeChanged
        :args:
            :sip:ref:`~PyQt6.QtCore.QSize`
        :description: QtWidgets/QRhiWidget-fixedColorBufferSizeChanged-s.rst

    .. sip:signal:: PyQt6.QtWidgets.QRhiWidget.frameSubmitted
        :description: QtWidgets/QRhiWidget-frameSubmitted-s.rst

    .. sip:signal:: PyQt6.QtWidgets.QRhiWidget.mirrorVerticallyChanged
        :args:
            bool
        :description: QtWidgets/QRhiWidget-mirrorVerticallyChanged-s.rst

    .. sip:signal:: PyQt6.QtWidgets.QRhiWidget.renderFailed
        :description: QtWidgets/QRhiWidget-renderFailed-s.rst

    .. sip:signal:: PyQt6.QtWidgets.QRhiWidget.sampleCountChanged
        :args:
            int
        :description: QtWidgets/QRhiWidget-sampleCountChanged-s.rst
