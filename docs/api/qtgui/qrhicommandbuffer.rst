:orphan:

.. sip:class:: PyQt6.QtGui.QRhiCommandBuffer
    :inherits: :sip:ref:`~PyQt6.QtGui.QRhiResource`
    :description: QtGui/QRhiCommandBuffer-c.rst

    .. sip:enum:: PyQt6.QtGui.QRhiCommandBuffer.BeginPassFlag
        :description: QtGui/QRhiCommandBuffer-BeginPassFlag-e.rst

        .. sip:enum-member:: PyQt6.QtGui.QRhiCommandBuffer.BeginPassFlag.DoNotTrackResourcesForCompute
            :description: QtGui/QRhiCommandBuffer-BeginPassFlag-DoNotTrackResourcesForCompute-v.rst

        .. sip:enum-member:: PyQt6.QtGui.QRhiCommandBuffer.BeginPassFlag.ExternalContent
            :description: QtGui/QRhiCommandBuffer-BeginPassFlag-ExternalContent-v.rst

    .. sip:enum:: PyQt6.QtGui.QRhiCommandBuffer.IndexFormat
        :description: QtGui/QRhiCommandBuffer-IndexFormat-e.rst

        .. sip:enum-member:: PyQt6.QtGui.QRhiCommandBuffer.IndexFormat.IndexUInt16
            :description: QtGui/QRhiCommandBuffer-IndexFormat-IndexUInt16-v.rst

        .. sip:enum-member:: PyQt6.QtGui.QRhiCommandBuffer.IndexFormat.IndexUInt32
            :description: QtGui/QRhiCommandBuffer-IndexFormat-IndexUInt32-v.rst

    .. sip:method:: PyQt6.QtGui.QRhiCommandBuffer.beginComputePass
        :args:
            resourceUpdates: :sip:ref:`~PyQt6.QtGui.QRhiResourceUpdateBatch` = None
            flags: :sip:ref:`~PyQt6.QtGui.QRhiCommandBuffer.BeginPassFlag` = {}
        :description: QtGui/QRhiCommandBuffer-beginComputePass-f.rst

    .. sip:method:: PyQt6.QtGui.QRhiCommandBuffer.beginExternal
        :description: QtGui/QRhiCommandBuffer-beginExternal-f.rst

    .. sip:method:: PyQt6.QtGui.QRhiCommandBuffer.beginPass
        :args:
            :sip:ref:`~PyQt6.QtGui.QRhiRenderTarget`
            :sip:ref:`~PyQt6.QtGui.QColor`|:sip:ref:`~PyQt6.QtCore.Qt.GlobalColor`|int
            :sip:ref:`~PyQt6.QtGui.QRhiDepthStencilClearValue`
            resourceUpdates: :sip:ref:`~PyQt6.QtGui.QRhiResourceUpdateBatch` = None
            flags: :sip:ref:`~PyQt6.QtGui.QRhiCommandBuffer.BeginPassFlag` = {}
        :description: QtGui/QRhiCommandBuffer-beginPass-f.rst

    .. sip:method:: PyQt6.QtGui.QRhiCommandBuffer.debugMarkBegin
        :args:
            :sip:ref:`~PyQt6.QtCore.QByteArray`|bytes|bytearray|memoryview
        :description: QtGui/QRhiCommandBuffer-debugMarkBegin-f.rst

    .. sip:method:: PyQt6.QtGui.QRhiCommandBuffer.debugMarkEnd
        :description: QtGui/QRhiCommandBuffer-debugMarkEnd-f.rst

    .. sip:method:: PyQt6.QtGui.QRhiCommandBuffer.debugMarkMsg
        :args:
            :sip:ref:`~PyQt6.QtCore.QByteArray`|bytes|bytearray|memoryview
        :description: QtGui/QRhiCommandBuffer-debugMarkMsg-f.rst

    .. sip:method:: PyQt6.QtGui.QRhiCommandBuffer.dispatch
        :args:
            int
            int
            int
        :description: QtGui/QRhiCommandBuffer-dispatch-f.rst

    .. sip:method:: PyQt6.QtGui.QRhiCommandBuffer.draw
        :args:
            int
            instanceCount: int = 1
            firstVertex: int = 0
            firstInstance: int = 0
        :description: QtGui/QRhiCommandBuffer-draw-f.rst

    .. sip:method:: PyQt6.QtGui.QRhiCommandBuffer.drawIndexed
        :args:
            int
            instanceCount: int = 1
            firstIndex: int = 0
            vertexOffset: int = 0
            firstInstance: int = 0
        :description: QtGui/QRhiCommandBuffer-drawIndexed-f.rst

    .. sip:method:: PyQt6.QtGui.QRhiCommandBuffer.drawIndexedIndirect
        :args:
            :sip:ref:`~PyQt6.QtGui.QRhiBuffer`
            int
            int
            stride: int = sizeof(QRhiIndexedIndirectDrawCommand)
        :description: QtGui/QRhiCommandBuffer-drawIndexedIndirect-f.rst

    .. sip:method:: PyQt6.QtGui.QRhiCommandBuffer.drawIndirect
        :args:
            :sip:ref:`~PyQt6.QtGui.QRhiBuffer`
            int
            int
            stride: int = sizeof(QRhiIndirectDrawCommand)
        :description: QtGui/QRhiCommandBuffer-drawIndirect-f.rst

    .. sip:method:: PyQt6.QtGui.QRhiCommandBuffer.endComputePass
        :args:
            resourceUpdates: :sip:ref:`~PyQt6.QtGui.QRhiResourceUpdateBatch` = None
        :description: QtGui/QRhiCommandBuffer-endComputePass-f.rst

    .. sip:method:: PyQt6.QtGui.QRhiCommandBuffer.endExternal
        :description: QtGui/QRhiCommandBuffer-endExternal-f.rst

    .. sip:method:: PyQt6.QtGui.QRhiCommandBuffer.endPass
        :args:
            resourceUpdates: :sip:ref:`~PyQt6.QtGui.QRhiResourceUpdateBatch` = None
        :description: QtGui/QRhiCommandBuffer-endPass-f.rst

    .. sip:method:: PyQt6.QtGui.QRhiCommandBuffer.lastCompletedGpuTime
        :returns:
            float
        :description: QtGui/QRhiCommandBuffer-lastCompletedGpuTime-f.rst

    .. sip:method:: PyQt6.QtGui.QRhiCommandBuffer.nativeHandles
        :returns:
            :sip:ref:`~PyQt6.QtGui.QRhiNativeHandles`
        :description: QtGui/QRhiCommandBuffer-nativeHandles-f.rst

    .. sip:method:: PyQt6.QtGui.QRhiCommandBuffer.resourceType
        :returns:
            :sip:ref:`~PyQt6.QtGui.QRhiResource.Type`
        :description: QtGui/QRhiCommandBuffer-resourceType-f.rst

    .. sip:method:: PyQt6.QtGui.QRhiCommandBuffer.resourceUpdate
        :args:
            :sip:ref:`~PyQt6.QtGui.QRhiResourceUpdateBatch`
        :description: QtGui/QRhiCommandBuffer-resourceUpdate-f.rst

    .. sip:method:: PyQt6.QtGui.QRhiCommandBuffer.setBlendConstants
        :args:
            :sip:ref:`~PyQt6.QtGui.QColor`|:sip:ref:`~PyQt6.QtCore.Qt.GlobalColor`|int
        :description: QtGui/QRhiCommandBuffer-setBlendConstants-f.rst

    .. sip:method:: PyQt6.QtGui.QRhiCommandBuffer.setComputePipeline
        :args:
            :sip:ref:`~PyQt6.QtGui.QRhiComputePipeline`
        :description: QtGui/QRhiCommandBuffer-setComputePipeline-f.rst

    .. sip:method:: PyQt6.QtGui.QRhiCommandBuffer.setGraphicsPipeline
        :args:
            :sip:ref:`~PyQt6.QtGui.QRhiGraphicsPipeline`
        :description: QtGui/QRhiCommandBuffer-setGraphicsPipeline-f.rst

    .. sip:method:: PyQt6.QtGui.QRhiCommandBuffer.setScissor
        :args:
            :sip:ref:`~PyQt6.QtGui.QRhiScissor`
        :description: QtGui/QRhiCommandBuffer-setScissor-f.rst

    .. sip:method:: PyQt6.QtGui.QRhiCommandBuffer.setShaderResources
        :args:
            srb: :sip:ref:`~PyQt6.QtGui.QRhiShaderResourceBindings` = None
            dynamicOffsets: tuple[int, int] = None
        :description: QtGui/QRhiCommandBuffer-setShaderResources-f.rst

    .. sip:method:: PyQt6.QtGui.QRhiCommandBuffer.setShadingRate
        :args:
            :sip:ref:`~PyQt6.QtCore.QSize`
        :description: QtGui/QRhiCommandBuffer-setShadingRate-f.rst

    .. sip:method:: PyQt6.QtGui.QRhiCommandBuffer.setStencilRef
        :args:
            int
        :description: QtGui/QRhiCommandBuffer-setStencilRef-f.rst

    .. sip:method:: PyQt6.QtGui.QRhiCommandBuffer.setVertexInput
        :args:
            int
            tuple[:sip:ref:`~PyQt6.QtGui.QRhiBuffer`, int]
            indexBuf: :sip:ref:`~PyQt6.QtGui.QRhiBuffer` = None
            indexOffset: int = 0
            indexFormat: :sip:ref:`~PyQt6.QtGui.QRhiCommandBuffer.IndexFormat` = :sip:ref:`~PyQt6.QtGui.QRhiCommandBuffer.IndexFormat.IndexUInt16`
        :description: QtGui/QRhiCommandBuffer-setVertexInput-f.rst

    .. sip:method:: PyQt6.QtGui.QRhiCommandBuffer.setViewport
        :args:
            :sip:ref:`~PyQt6.QtGui.QRhiViewport`
        :description: QtGui/QRhiCommandBuffer-setViewport-f.rst
