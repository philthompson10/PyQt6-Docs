:orphan:

.. sip:class:: PyQt6.QtGui.QShader
    :description: QtGui/QShader-c.rst

    .. sip:enum:: PyQt6.QtGui.QShader.SerializedFormatVersion
        :description: QtGui/QShader-SerializedFormatVersion-e.rst

        .. sip:enum-member:: PyQt6.QtGui.QShader.SerializedFormatVersion.Latest
            :description: QtGui/QShader-SerializedFormatVersion-Latest-v.rst

        .. sip:enum-member:: PyQt6.QtGui.QShader.SerializedFormatVersion.Qt_6_4
            :description: QtGui/QShader-SerializedFormatVersion-Qt_6_4-v.rst

        .. sip:enum-member:: PyQt6.QtGui.QShader.SerializedFormatVersion.Qt_6_5
            :description: QtGui/QShader-SerializedFormatVersion-Qt_6_5-v.rst

    .. sip:enum:: PyQt6.QtGui.QShader.Source
        :description: QtGui/QShader-Source-e.rst

        .. sip:enum-member:: PyQt6.QtGui.QShader.Source.DxbcShader
            :description: QtGui/QShader-Source-DxbcShader-v.rst

        .. sip:enum-member:: PyQt6.QtGui.QShader.Source.DxilShader
            :description: QtGui/QShader-Source-DxilShader-v.rst

        .. sip:enum-member:: PyQt6.QtGui.QShader.Source.GlslShader
            :description: QtGui/QShader-Source-GlslShader-v.rst

        .. sip:enum-member:: PyQt6.QtGui.QShader.Source.HlslShader
            :description: QtGui/QShader-Source-HlslShader-v.rst

        .. sip:enum-member:: PyQt6.QtGui.QShader.Source.MetalLibShader
            :description: QtGui/QShader-Source-MetalLibShader-v.rst

        .. sip:enum-member:: PyQt6.QtGui.QShader.Source.MslShader
            :description: QtGui/QShader-Source-MslShader-v.rst

        .. sip:enum-member:: PyQt6.QtGui.QShader.Source.SpirvShader
            :description: QtGui/QShader-Source-SpirvShader-v.rst

        .. sip:enum-member:: PyQt6.QtGui.QShader.Source.WgslShader
            :description: QtGui/QShader-Source-WgslShader-v.rst

    .. sip:enum:: PyQt6.QtGui.QShader.Stage
        :description: QtGui/QShader-Stage-e.rst

        .. sip:enum-member:: PyQt6.QtGui.QShader.Stage.ComputeStage
            :description: QtGui/QShader-Stage-ComputeStage-v.rst

        .. sip:enum-member:: PyQt6.QtGui.QShader.Stage.FragmentStage
            :description: QtGui/QShader-Stage-FragmentStage-v.rst

        .. sip:enum-member:: PyQt6.QtGui.QShader.Stage.GeometryStage
            :description: QtGui/QShader-Stage-GeometryStage-v.rst

        .. sip:enum-member:: PyQt6.QtGui.QShader.Stage.TessellationControlStage
            :description: QtGui/QShader-Stage-TessellationControlStage-v.rst

        .. sip:enum-member:: PyQt6.QtGui.QShader.Stage.TessellationEvaluationStage
            :description: QtGui/QShader-Stage-TessellationEvaluationStage-v.rst

        .. sip:enum-member:: PyQt6.QtGui.QShader.Stage.VertexStage
            :description: QtGui/QShader-Stage-VertexStage-v.rst

    .. sip:enum:: PyQt6.QtGui.QShader.Variant
        :description: QtGui/QShader-Variant-e.rst

        .. sip:enum-member:: PyQt6.QtGui.QShader.Variant.BatchableVertexShader
            :description: QtGui/QShader-Variant-BatchableVertexShader-v.rst

        .. sip:enum-member:: PyQt6.QtGui.QShader.Variant.HdrCapableFragmentShader
            :description: QtGui/QShader-Variant-HdrCapableFragmentShader-v.rst

        .. sip:enum-member:: PyQt6.QtGui.QShader.Variant.NonIndexedVertexAsComputeShader
            :description: QtGui/QShader-Variant-NonIndexedVertexAsComputeShader-v.rst

        .. sip:enum-member:: PyQt6.QtGui.QShader.Variant.StandardShader
            :description: QtGui/QShader-Variant-StandardShader-v.rst

        .. sip:enum-member:: PyQt6.QtGui.QShader.Variant.UInt16IndexedVertexAsComputeShader
            :description: QtGui/QShader-Variant-UInt16IndexedVertexAsComputeShader-v.rst

        .. sip:enum-member:: PyQt6.QtGui.QShader.Variant.UInt32IndexedVertexAsComputeShader
            :description: QtGui/QShader-Variant-UInt32IndexedVertexAsComputeShader-v.rst

    .. sip:method:: PyQt6.QtGui.QShader.__init__
        :description: QtGui/QShader-__init__-f.rst

    .. sip:method:: PyQt6.QtGui.QShader.__init__
        :args:
            :sip:ref:`~PyQt6.QtGui.QShader`
        :description: QtGui/QShader-__init__-f-1.rst

    .. sip:method:: PyQt6.QtGui.QShader.availableShaders
        :returns:
            list[:sip:ref:`~PyQt6.QtGui.QShaderKey`]
        :description: QtGui/QShader-availableShaders-f.rst

    .. sip:method:: PyQt6.QtGui.QShader.description
        :returns:
            :sip:ref:`~PyQt6.QtGui.QShaderDescription`
        :description: QtGui/QShader-description-f.rst

    .. sip:method:: PyQt6.QtGui.QShader.__eq__
        :args:
            :sip:ref:`~PyQt6.QtGui.QShader`
        :returns:
            bool
        :description: QtGui/QShader-__eq__-f.rst

    .. sip:method:: PyQt6.QtGui.QShader.fromSerialized
        :args:
            :sip:ref:`~PyQt6.QtCore.QByteArray`|bytes|bytearray|memoryview
        :returns:
            :sip:ref:`~PyQt6.QtGui.QShader`
        :static:
        :description: QtGui/QShader-fromSerialized-f.rst

    .. sip:method:: PyQt6.QtGui.QShader.__hash__
        :returns:
            int
        :description: QtGui/QShader-__hash__-f.rst

    .. sip:method:: PyQt6.QtGui.QShader.isValid
        :returns:
            bool
        :description: QtGui/QShader-isValid-f.rst

    .. sip:method:: PyQt6.QtGui.QShader.nativeResourceBindingMap
        :args:
            :sip:ref:`~PyQt6.QtGui.QShaderKey`
        :returns:
            dict[int, tuple[int, int]]
        :description: QtGui/QShader-nativeResourceBindingMap-f.rst

    .. sip:method:: PyQt6.QtGui.QShader.nativeShaderInfo
        :args:
            :sip:ref:`~PyQt6.QtGui.QShaderKey`
        :returns:
            :sip:ref:`~PyQt6.QtGui.QShader.NativeShaderInfo`
        :description: QtGui/QShader-nativeShaderInfo-f.rst

    .. sip:method:: PyQt6.QtGui.QShader.__ne__
        :args:
            :sip:ref:`~PyQt6.QtGui.QShader`
        :returns:
            bool
        :description: QtGui/QShader-__ne__-f.rst

    .. sip:method:: PyQt6.QtGui.QShader.removeNativeShaderInfo
        :args:
            :sip:ref:`~PyQt6.QtGui.QShaderKey`
        :description: QtGui/QShader-removeNativeShaderInfo-f.rst

    .. sip:method:: PyQt6.QtGui.QShader.removeResourceBindingMap
        :args:
            :sip:ref:`~PyQt6.QtGui.QShaderKey`
        :description: QtGui/QShader-removeResourceBindingMap-f.rst

    .. sip:method:: PyQt6.QtGui.QShader.removeSeparateToCombinedImageSamplerMappingList
        :args:
            :sip:ref:`~PyQt6.QtGui.QShaderKey`
        :description: QtGui/QShader-removeSeparateToCombinedImageSamplerMappingList-f.rst

    .. sip:method:: PyQt6.QtGui.QShader.removeShader
        :args:
            :sip:ref:`~PyQt6.QtGui.QShaderKey`
        :description: QtGui/QShader-removeShader-f.rst

    .. sip:method:: PyQt6.QtGui.QShader.separateToCombinedImageSamplerMappingList
        :args:
            :sip:ref:`~PyQt6.QtGui.QShaderKey`
        :returns:
            list[:sip:ref:`~PyQt6.QtGui.QShader.SeparateToCombinedImageSamplerMapping`]
        :description: QtGui/QShader-separateToCombinedImageSamplerMappingList-f.rst

    .. sip:method:: PyQt6.QtGui.QShader.serialized
        :args:
            version: :sip:ref:`~PyQt6.QtGui.QShader.SerializedFormatVersion` = :sip:ref:`~PyQt6.QtGui.QShader.SerializedFormatVersion.Latest`
        :returns:
            :sip:ref:`~PyQt6.QtCore.QByteArray`
        :description: QtGui/QShader-serialized-f.rst

    .. sip:method:: PyQt6.QtGui.QShader.setDescription
        :args:
            :sip:ref:`~PyQt6.QtGui.QShaderDescription`
        :description: QtGui/QShader-setDescription-f.rst

    .. sip:method:: PyQt6.QtGui.QShader.setNativeShaderInfo
        :args:
            :sip:ref:`~PyQt6.QtGui.QShaderKey`
            :sip:ref:`~PyQt6.QtGui.QShader.NativeShaderInfo`
        :description: QtGui/QShader-setNativeShaderInfo-f.rst

    .. sip:method:: PyQt6.QtGui.QShader.setResourceBindingMap
        :args:
            :sip:ref:`~PyQt6.QtGui.QShaderKey`
            dict[int, tuple[int, int]]
        :description: QtGui/QShader-setResourceBindingMap-f.rst

    .. sip:method:: PyQt6.QtGui.QShader.setSeparateToCombinedImageSamplerMappingList
        :args:
            :sip:ref:`~PyQt6.QtGui.QShaderKey`
            Iterable[:sip:ref:`~PyQt6.QtGui.QShader.SeparateToCombinedImageSamplerMapping`]
        :description: QtGui/QShader-setSeparateToCombinedImageSamplerMappingList-f.rst

    .. sip:method:: PyQt6.QtGui.QShader.setShader
        :args:
            :sip:ref:`~PyQt6.QtGui.QShaderKey`
            :sip:ref:`~PyQt6.QtGui.QShaderCode`
        :description: QtGui/QShader-setShader-f.rst

    .. sip:method:: PyQt6.QtGui.QShader.setStage
        :args:
            :sip:ref:`~PyQt6.QtGui.QShader.Stage`
        :description: QtGui/QShader-setStage-f.rst

    .. sip:method:: PyQt6.QtGui.QShader.shader
        :args:
            :sip:ref:`~PyQt6.QtGui.QShaderKey`
        :returns:
            :sip:ref:`~PyQt6.QtGui.QShaderCode`
        :description: QtGui/QShader-shader-f.rst

    .. sip:method:: PyQt6.QtGui.QShader.stage
        :returns:
            :sip:ref:`~PyQt6.QtGui.QShader.Stage`
        :description: QtGui/QShader-stage-f.rst

    .. sip:method:: PyQt6.QtGui.QShader.swap
        :args:
            :sip:ref:`~PyQt6.QtGui.QShader`
        :description: QtGui/QShader-swap-f.rst
