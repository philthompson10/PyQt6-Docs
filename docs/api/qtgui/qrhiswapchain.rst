:orphan:

.. sip:class:: PyQt6.QtGui.QRhiSwapChain
    :inherits: :sip:ref:`~PyQt6.QtGui.QRhiResource`
    :description: QtGui/QRhiSwapChain-c.rst

    .. sip:enum:: PyQt6.QtGui.QRhiSwapChain.Flag
        :description: QtGui/QRhiSwapChain-Flag-e.rst

        .. sip:enum-member:: PyQt6.QtGui.QRhiSwapChain.Flag.MinimalBufferCount
            :description: QtGui/QRhiSwapChain-Flag-MinimalBufferCount-v.rst

        .. sip:enum-member:: PyQt6.QtGui.QRhiSwapChain.Flag.NoVSync
            :description: QtGui/QRhiSwapChain-Flag-NoVSync-v.rst

        .. sip:enum-member:: PyQt6.QtGui.QRhiSwapChain.Flag.sRGB
            :description: QtGui/QRhiSwapChain-Flag-sRGB-v.rst

        .. sip:enum-member:: PyQt6.QtGui.QRhiSwapChain.Flag.SurfaceHasNonPreMulAlpha
            :description: QtGui/QRhiSwapChain-Flag-SurfaceHasNonPreMulAlpha-v.rst

        .. sip:enum-member:: PyQt6.QtGui.QRhiSwapChain.Flag.SurfaceHasPreMulAlpha
            :description: QtGui/QRhiSwapChain-Flag-SurfaceHasPreMulAlpha-v.rst

        .. sip:enum-member:: PyQt6.QtGui.QRhiSwapChain.Flag.UsedAsTransferSource
            :description: QtGui/QRhiSwapChain-Flag-UsedAsTransferSource-v.rst

    .. sip:enum:: PyQt6.QtGui.QRhiSwapChain.Format
        :description: QtGui/QRhiSwapChain-Format-e.rst

        .. sip:enum-member:: PyQt6.QtGui.QRhiSwapChain.Format.HDR10
            :description: QtGui/QRhiSwapChain-Format-HDR10-v.rst

        .. sip:enum-member:: PyQt6.QtGui.QRhiSwapChain.Format.HDRExtendedDisplayP3Linear
            :description: QtGui/QRhiSwapChain-Format-HDRExtendedDisplayP3Linear-v.rst

        .. sip:enum-member:: PyQt6.QtGui.QRhiSwapChain.Format.HDRExtendedSrgbLinear
            :description: QtGui/QRhiSwapChain-Format-HDRExtendedSrgbLinear-v.rst

        .. sip:enum-member:: PyQt6.QtGui.QRhiSwapChain.Format.SDR
            :description: QtGui/QRhiSwapChain-Format-SDR-v.rst

    .. sip:enum:: PyQt6.QtGui.QRhiSwapChain.StereoTargetBuffer
        :description: QtGui/QRhiSwapChain-StereoTargetBuffer-e.rst

        .. sip:enum-member:: PyQt6.QtGui.QRhiSwapChain.StereoTargetBuffer.LeftBuffer
            :description: QtGui/QRhiSwapChain-StereoTargetBuffer-LeftBuffer-v.rst

        .. sip:enum-member:: PyQt6.QtGui.QRhiSwapChain.StereoTargetBuffer.RightBuffer
            :description: QtGui/QRhiSwapChain-StereoTargetBuffer-RightBuffer-v.rst

    .. sip:method:: PyQt6.QtGui.QRhiSwapChain.createOrResize
        :returns:
            bool
        :description: QtGui/QRhiSwapChain-createOrResize-f.rst

    .. sip:method:: PyQt6.QtGui.QRhiSwapChain.currentFrameCommandBuffer
        :returns:
            :sip:ref:`~PyQt6.QtGui.QRhiCommandBuffer`
        :description: QtGui/QRhiSwapChain-currentFrameCommandBuffer-f.rst

    .. sip:method:: PyQt6.QtGui.QRhiSwapChain.currentFrameRenderTarget
        :returns:
            :sip:ref:`~PyQt6.QtGui.QRhiRenderTarget`
        :description: QtGui/QRhiSwapChain-currentFrameRenderTarget-f.rst

    .. sip:method:: PyQt6.QtGui.QRhiSwapChain.currentFrameRenderTarget
        :args:
            :sip:ref:`~PyQt6.QtGui.QRhiSwapChain.StereoTargetBuffer`
        :returns:
            :sip:ref:`~PyQt6.QtGui.QRhiRenderTarget`
        :description: QtGui/QRhiSwapChain-currentFrameRenderTarget-f-1.rst

    .. sip:method:: PyQt6.QtGui.QRhiSwapChain.currentPixelSize
        :returns:
            :sip:ref:`~PyQt6.QtCore.QSize`
        :description: QtGui/QRhiSwapChain-currentPixelSize-f.rst

    .. sip:method:: PyQt6.QtGui.QRhiSwapChain.depthStencil
        :returns:
            :sip:ref:`~PyQt6.QtGui.QRhiRenderBuffer`
        :description: QtGui/QRhiSwapChain-depthStencil-f.rst

    .. sip:method:: PyQt6.QtGui.QRhiSwapChain.flags
        :returns:
            :sip:ref:`~PyQt6.QtGui.QRhiSwapChain.Flag`
        :description: QtGui/QRhiSwapChain-flags-f.rst

    .. sip:method:: PyQt6.QtGui.QRhiSwapChain.format
        :returns:
            :sip:ref:`~PyQt6.QtGui.QRhiSwapChain.Format`
        :description: QtGui/QRhiSwapChain-format-f.rst

    .. sip:method:: PyQt6.QtGui.QRhiSwapChain.hdrInfo
        :returns:
            :sip:ref:`~PyQt6.QtGui.QRhiSwapChainHdrInfo`
        :description: QtGui/QRhiSwapChain-hdrInfo-f.rst

    .. sip:method:: PyQt6.QtGui.QRhiSwapChain.isFormatSupported
        :args:
            :sip:ref:`~PyQt6.QtGui.QRhiSwapChain.Format`
        :returns:
            bool
        :description: QtGui/QRhiSwapChain-isFormatSupported-f.rst

    .. sip:method:: PyQt6.QtGui.QRhiSwapChain.newCompatibleRenderPassDescriptor
        :returns:
            :sip:ref:`~PyQt6.QtGui.QRhiRenderPassDescriptor`
        :description: QtGui/QRhiSwapChain-newCompatibleRenderPassDescriptor-f.rst

    .. sip:method:: PyQt6.QtGui.QRhiSwapChain.proxyData
        :returns:
            :sip:ref:`~PyQt6.QtGui.QRhiSwapChainProxyData`
        :description: QtGui/QRhiSwapChain-proxyData-f.rst

    .. sip:method:: PyQt6.QtGui.QRhiSwapChain.renderPassDescriptor
        :returns:
            :sip:ref:`~PyQt6.QtGui.QRhiRenderPassDescriptor`
        :description: QtGui/QRhiSwapChain-renderPassDescriptor-f.rst

    .. sip:method:: PyQt6.QtGui.QRhiSwapChain.resourceType
        :returns:
            :sip:ref:`~PyQt6.QtGui.QRhiResource.Type`
        :description: QtGui/QRhiSwapChain-resourceType-f.rst

    .. sip:method:: PyQt6.QtGui.QRhiSwapChain.sampleCount
        :returns:
            int
        :description: QtGui/QRhiSwapChain-sampleCount-f.rst

    .. sip:method:: PyQt6.QtGui.QRhiSwapChain.setDepthStencil
        :args:
            :sip:ref:`~PyQt6.QtGui.QRhiRenderBuffer`
        :description: QtGui/QRhiSwapChain-setDepthStencil-f.rst

    .. sip:method:: PyQt6.QtGui.QRhiSwapChain.setFlags
        :args:
            :sip:ref:`~PyQt6.QtGui.QRhiSwapChain.Flag`
        :description: QtGui/QRhiSwapChain-setFlags-f.rst

    .. sip:method:: PyQt6.QtGui.QRhiSwapChain.setFormat
        :args:
            :sip:ref:`~PyQt6.QtGui.QRhiSwapChain.Format`
        :description: QtGui/QRhiSwapChain-setFormat-f.rst

    .. sip:method:: PyQt6.QtGui.QRhiSwapChain.setProxyData
        :args:
            :sip:ref:`~PyQt6.QtGui.QRhiSwapChainProxyData`
        :description: QtGui/QRhiSwapChain-setProxyData-f.rst

    .. sip:method:: PyQt6.QtGui.QRhiSwapChain.setRenderPassDescriptor
        :args:
            :sip:ref:`~PyQt6.QtGui.QRhiRenderPassDescriptor`
        :description: QtGui/QRhiSwapChain-setRenderPassDescriptor-f.rst

    .. sip:method:: PyQt6.QtGui.QRhiSwapChain.setSampleCount
        :args:
            int
        :description: QtGui/QRhiSwapChain-setSampleCount-f.rst

    .. sip:method:: PyQt6.QtGui.QRhiSwapChain.setShadingRateMap
        :args:
            :sip:ref:`~PyQt6.QtGui.QRhiShadingRateMap`
        :description: QtGui/QRhiSwapChain-setShadingRateMap-f.rst

    .. sip:method:: PyQt6.QtGui.QRhiSwapChain.setWindow
        :args:
            :sip:ref:`~PyQt6.QtGui.QWindow`
        :description: QtGui/QRhiSwapChain-setWindow-f.rst

    .. sip:method:: PyQt6.QtGui.QRhiSwapChain.shadingRateMap
        :returns:
            :sip:ref:`~PyQt6.QtGui.QRhiShadingRateMap`
        :description: QtGui/QRhiSwapChain-shadingRateMap-f.rst

    .. sip:method:: PyQt6.QtGui.QRhiSwapChain.surfacePixelSize
        :returns:
            :sip:ref:`~PyQt6.QtCore.QSize`
        :description: QtGui/QRhiSwapChain-surfacePixelSize-f.rst

    .. sip:method:: PyQt6.QtGui.QRhiSwapChain.window
        :returns:
            :sip:ref:`~PyQt6.QtGui.QWindow`
        :description: QtGui/QRhiSwapChain-window-f.rst
