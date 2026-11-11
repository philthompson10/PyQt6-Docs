:orphan:

.. sip:class:: PyQt6.QtGui.QRhiTexture
    :inherits: :sip:ref:`~PyQt6.QtGui.QRhiResource`
    :description: QtGui/QRhiTexture-c.rst

    .. sip:enum:: PyQt6.QtGui.QRhiTexture.Flag
        :description: QtGui/QRhiTexture-Flag-e.rst

        .. sip:enum-member:: PyQt6.QtGui.QRhiTexture.Flag.CubeMap
            :description: QtGui/QRhiTexture-Flag-CubeMap-v.rst

        .. sip:enum-member:: PyQt6.QtGui.QRhiTexture.Flag.ExternalOES
            :description: QtGui/QRhiTexture-Flag-ExternalOES-v.rst

        .. sip:enum-member:: PyQt6.QtGui.QRhiTexture.Flag.MipMapped
            :description: QtGui/QRhiTexture-Flag-MipMapped-v.rst

        .. sip:enum-member:: PyQt6.QtGui.QRhiTexture.Flag.OneDimensional
            :description: QtGui/QRhiTexture-Flag-OneDimensional-v.rst

        .. sip:enum-member:: PyQt6.QtGui.QRhiTexture.Flag.RenderTarget
            :description: QtGui/QRhiTexture-Flag-RenderTarget-v.rst

        .. sip:enum-member:: PyQt6.QtGui.QRhiTexture.Flag.sRGB
            :description: QtGui/QRhiTexture-Flag-sRGB-v.rst

        .. sip:enum-member:: PyQt6.QtGui.QRhiTexture.Flag.TextureArray
            :description: QtGui/QRhiTexture-Flag-TextureArray-v.rst

        .. sip:enum-member:: PyQt6.QtGui.QRhiTexture.Flag.TextureRectangleGL
            :description: QtGui/QRhiTexture-Flag-TextureRectangleGL-v.rst

        .. sip:enum-member:: PyQt6.QtGui.QRhiTexture.Flag.ThreeDimensional
            :description: QtGui/QRhiTexture-Flag-ThreeDimensional-v.rst

        .. sip:enum-member:: PyQt6.QtGui.QRhiTexture.Flag.UsedAsCompressedAtlas
            :description: QtGui/QRhiTexture-Flag-UsedAsCompressedAtlas-v.rst

        .. sip:enum-member:: PyQt6.QtGui.QRhiTexture.Flag.UsedAsShadingRateMap
            :description: QtGui/QRhiTexture-Flag-UsedAsShadingRateMap-v.rst

        .. sip:enum-member:: PyQt6.QtGui.QRhiTexture.Flag.UsedAsTransferSource
            :description: QtGui/QRhiTexture-Flag-UsedAsTransferSource-v.rst

        .. sip:enum-member:: PyQt6.QtGui.QRhiTexture.Flag.UsedWithGenerateMips
            :description: QtGui/QRhiTexture-Flag-UsedWithGenerateMips-v.rst

        .. sip:enum-member:: PyQt6.QtGui.QRhiTexture.Flag.UsedWithLoadStore
            :description: QtGui/QRhiTexture-Flag-UsedWithLoadStore-v.rst

    .. sip:enum:: PyQt6.QtGui.QRhiTexture.Format
        :description: QtGui/QRhiTexture-Format-e.rst

        .. sip:enum-member:: PyQt6.QtGui.QRhiTexture.Format.ASTC_10x10
            :description: QtGui/QRhiTexture-Format-ASTC_10x10-v.rst

        .. sip:enum-member:: PyQt6.QtGui.QRhiTexture.Format.ASTC_10x5
            :description: QtGui/QRhiTexture-Format-ASTC_10x5-v.rst

        .. sip:enum-member:: PyQt6.QtGui.QRhiTexture.Format.ASTC_10x6
            :description: QtGui/QRhiTexture-Format-ASTC_10x6-v.rst

        .. sip:enum-member:: PyQt6.QtGui.QRhiTexture.Format.ASTC_10x8
            :description: QtGui/QRhiTexture-Format-ASTC_10x8-v.rst

        .. sip:enum-member:: PyQt6.QtGui.QRhiTexture.Format.ASTC_12x10
            :description: QtGui/QRhiTexture-Format-ASTC_12x10-v.rst

        .. sip:enum-member:: PyQt6.QtGui.QRhiTexture.Format.ASTC_12x12
            :description: QtGui/QRhiTexture-Format-ASTC_12x12-v.rst

        .. sip:enum-member:: PyQt6.QtGui.QRhiTexture.Format.ASTC_4x4
            :description: QtGui/QRhiTexture-Format-ASTC_4x4-v.rst

        .. sip:enum-member:: PyQt6.QtGui.QRhiTexture.Format.ASTC_5x4
            :description: QtGui/QRhiTexture-Format-ASTC_5x4-v.rst

        .. sip:enum-member:: PyQt6.QtGui.QRhiTexture.Format.ASTC_5x5
            :description: QtGui/QRhiTexture-Format-ASTC_5x5-v.rst

        .. sip:enum-member:: PyQt6.QtGui.QRhiTexture.Format.ASTC_6x5
            :description: QtGui/QRhiTexture-Format-ASTC_6x5-v.rst

        .. sip:enum-member:: PyQt6.QtGui.QRhiTexture.Format.ASTC_6x6
            :description: QtGui/QRhiTexture-Format-ASTC_6x6-v.rst

        .. sip:enum-member:: PyQt6.QtGui.QRhiTexture.Format.ASTC_8x5
            :description: QtGui/QRhiTexture-Format-ASTC_8x5-v.rst

        .. sip:enum-member:: PyQt6.QtGui.QRhiTexture.Format.ASTC_8x6
            :description: QtGui/QRhiTexture-Format-ASTC_8x6-v.rst

        .. sip:enum-member:: PyQt6.QtGui.QRhiTexture.Format.ASTC_8x8
            :description: QtGui/QRhiTexture-Format-ASTC_8x8-v.rst

        .. sip:enum-member:: PyQt6.QtGui.QRhiTexture.Format.BC1
            :description: QtGui/QRhiTexture-Format-BC1-v.rst

        .. sip:enum-member:: PyQt6.QtGui.QRhiTexture.Format.BC2
            :description: QtGui/QRhiTexture-Format-BC2-v.rst

        .. sip:enum-member:: PyQt6.QtGui.QRhiTexture.Format.BC3
            :description: QtGui/QRhiTexture-Format-BC3-v.rst

        .. sip:enum-member:: PyQt6.QtGui.QRhiTexture.Format.BC4
            :description: QtGui/QRhiTexture-Format-BC4-v.rst

        .. sip:enum-member:: PyQt6.QtGui.QRhiTexture.Format.BC5
            :description: QtGui/QRhiTexture-Format-BC5-v.rst

        .. sip:enum-member:: PyQt6.QtGui.QRhiTexture.Format.BC6H
            :description: QtGui/QRhiTexture-Format-BC6H-v.rst

        .. sip:enum-member:: PyQt6.QtGui.QRhiTexture.Format.BC7
            :description: QtGui/QRhiTexture-Format-BC7-v.rst

        .. sip:enum-member:: PyQt6.QtGui.QRhiTexture.Format.BGRA8
            :description: QtGui/QRhiTexture-Format-BGRA8-v.rst

        .. sip:enum-member:: PyQt6.QtGui.QRhiTexture.Format.D16
            :description: QtGui/QRhiTexture-Format-D16-v.rst

        .. sip:enum-member:: PyQt6.QtGui.QRhiTexture.Format.D24
            :description: QtGui/QRhiTexture-Format-D24-v.rst

        .. sip:enum-member:: PyQt6.QtGui.QRhiTexture.Format.D24S8
            :description: QtGui/QRhiTexture-Format-D24S8-v.rst

        .. sip:enum-member:: PyQt6.QtGui.QRhiTexture.Format.D32F
            :description: QtGui/QRhiTexture-Format-D32F-v.rst

        .. sip:enum-member:: PyQt6.QtGui.QRhiTexture.Format.D32FS8
            :description: QtGui/QRhiTexture-Format-D32FS8-v.rst

        .. sip:enum-member:: PyQt6.QtGui.QRhiTexture.Format.ETC2_RGB8
            :description: QtGui/QRhiTexture-Format-ETC2_RGB8-v.rst

        .. sip:enum-member:: PyQt6.QtGui.QRhiTexture.Format.ETC2_RGB8A1
            :description: QtGui/QRhiTexture-Format-ETC2_RGB8A1-v.rst

        .. sip:enum-member:: PyQt6.QtGui.QRhiTexture.Format.ETC2_RGBA8
            :description: QtGui/QRhiTexture-Format-ETC2_RGBA8-v.rst

        .. sip:enum-member:: PyQt6.QtGui.QRhiTexture.Format.R16
            :description: QtGui/QRhiTexture-Format-R16-v.rst

        .. sip:enum-member:: PyQt6.QtGui.QRhiTexture.Format.R16F
            :description: QtGui/QRhiTexture-Format-R16F-v.rst

        .. sip:enum-member:: PyQt6.QtGui.QRhiTexture.Format.R32F
            :description: QtGui/QRhiTexture-Format-R32F-v.rst

        .. sip:enum-member:: PyQt6.QtGui.QRhiTexture.Format.R32SI
            :description: QtGui/QRhiTexture-Format-R32SI-v.rst

        .. sip:enum-member:: PyQt6.QtGui.QRhiTexture.Format.R32UI
            :description: QtGui/QRhiTexture-Format-R32UI-v.rst

        .. sip:enum-member:: PyQt6.QtGui.QRhiTexture.Format.R8
            :description: QtGui/QRhiTexture-Format-R8-v.rst

        .. sip:enum-member:: PyQt6.QtGui.QRhiTexture.Format.R8SI
            :description: QtGui/QRhiTexture-Format-R8SI-v.rst

        .. sip:enum-member:: PyQt6.QtGui.QRhiTexture.Format.R8UI
            :description: QtGui/QRhiTexture-Format-R8UI-v.rst

        .. sip:enum-member:: PyQt6.QtGui.QRhiTexture.Format.RED_OR_ALPHA8
            :description: QtGui/QRhiTexture-Format-RED_OR_ALPHA8-v.rst

        .. sip:enum-member:: PyQt6.QtGui.QRhiTexture.Format.RG16
            :description: QtGui/QRhiTexture-Format-RG16-v.rst

        .. sip:enum-member:: PyQt6.QtGui.QRhiTexture.Format.RG32SI
            :description: QtGui/QRhiTexture-Format-RG32SI-v.rst

        .. sip:enum-member:: PyQt6.QtGui.QRhiTexture.Format.RG32UI
            :description: QtGui/QRhiTexture-Format-RG32UI-v.rst

        .. sip:enum-member:: PyQt6.QtGui.QRhiTexture.Format.RG8
            :description: QtGui/QRhiTexture-Format-RG8-v.rst

        .. sip:enum-member:: PyQt6.QtGui.QRhiTexture.Format.RGB10A2
            :description: QtGui/QRhiTexture-Format-RGB10A2-v.rst

        .. sip:enum-member:: PyQt6.QtGui.QRhiTexture.Format.RGBA16F
            :description: QtGui/QRhiTexture-Format-RGBA16F-v.rst

        .. sip:enum-member:: PyQt6.QtGui.QRhiTexture.Format.RGBA32F
            :description: QtGui/QRhiTexture-Format-RGBA32F-v.rst

        .. sip:enum-member:: PyQt6.QtGui.QRhiTexture.Format.RGBA32SI
            :description: QtGui/QRhiTexture-Format-RGBA32SI-v.rst

        .. sip:enum-member:: PyQt6.QtGui.QRhiTexture.Format.RGBA32UI
            :description: QtGui/QRhiTexture-Format-RGBA32UI-v.rst

        .. sip:enum-member:: PyQt6.QtGui.QRhiTexture.Format.RGBA8
            :description: QtGui/QRhiTexture-Format-RGBA8-v.rst

        .. sip:enum-member:: PyQt6.QtGui.QRhiTexture.Format.UnknownFormat
            :description: QtGui/QRhiTexture-Format-UnknownFormat-v.rst

    .. sip:method:: PyQt6.QtGui.QRhiTexture.arrayRangeLength
        :returns:
            int
        :description: QtGui/QRhiTexture-arrayRangeLength-f.rst

    .. sip:method:: PyQt6.QtGui.QRhiTexture.arrayRangeStart
        :returns:
            int
        :description: QtGui/QRhiTexture-arrayRangeStart-f.rst

    .. sip:method:: PyQt6.QtGui.QRhiTexture.arraySize
        :returns:
            int
        :description: QtGui/QRhiTexture-arraySize-f.rst

    .. sip:method:: PyQt6.QtGui.QRhiTexture.create
        :returns:
            bool
        :description: QtGui/QRhiTexture-create-f.rst

    .. sip:method:: PyQt6.QtGui.QRhiTexture.createFrom
        :args:
            :sip:ref:`~PyQt6.QtGui.QRhiTexture.NativeTexture`
        :returns:
            bool
        :description: QtGui/QRhiTexture-createFrom-f.rst

    .. sip:method:: PyQt6.QtGui.QRhiTexture.depth
        :returns:
            int
        :description: QtGui/QRhiTexture-depth-f.rst

    .. sip:method:: PyQt6.QtGui.QRhiTexture.flags
        :returns:
            :sip:ref:`~PyQt6.QtGui.QRhiTexture.Flag`
        :description: QtGui/QRhiTexture-flags-f.rst

    .. sip:method:: PyQt6.QtGui.QRhiTexture.format
        :returns:
            :sip:ref:`~PyQt6.QtGui.QRhiTexture.Format`
        :description: QtGui/QRhiTexture-format-f.rst

    .. sip:method:: PyQt6.QtGui.QRhiTexture.nativeTexture
        :returns:
            :sip:ref:`~PyQt6.QtGui.QRhiTexture.NativeTexture`
        :description: QtGui/QRhiTexture-nativeTexture-f.rst

    .. sip:method:: PyQt6.QtGui.QRhiTexture.pixelSize
        :returns:
            :sip:ref:`~PyQt6.QtCore.QSize`
        :description: QtGui/QRhiTexture-pixelSize-f.rst

    .. sip:method:: PyQt6.QtGui.QRhiTexture.readViewFormat
        :returns:
            :sip:ref:`~PyQt6.QtGui.QRhiTexture.ViewFormat`
        :description: QtGui/QRhiTexture-readViewFormat-f.rst

    .. sip:method:: PyQt6.QtGui.QRhiTexture.resourceType
        :returns:
            :sip:ref:`~PyQt6.QtGui.QRhiResource.Type`
        :description: QtGui/QRhiTexture-resourceType-f.rst

    .. sip:method:: PyQt6.QtGui.QRhiTexture.sampleCount
        :returns:
            int
        :description: QtGui/QRhiTexture-sampleCount-f.rst

    .. sip:method:: PyQt6.QtGui.QRhiTexture.setArrayRange
        :args:
            int
            int
        :description: QtGui/QRhiTexture-setArrayRange-f.rst

    .. sip:method:: PyQt6.QtGui.QRhiTexture.setArraySize
        :args:
            int
        :description: QtGui/QRhiTexture-setArraySize-f.rst

    .. sip:method:: PyQt6.QtGui.QRhiTexture.setDepth
        :args:
            int
        :description: QtGui/QRhiTexture-setDepth-f.rst

    .. sip:method:: PyQt6.QtGui.QRhiTexture.setFlags
        :args:
            :sip:ref:`~PyQt6.QtGui.QRhiTexture.Flag`
        :description: QtGui/QRhiTexture-setFlags-f.rst

    .. sip:method:: PyQt6.QtGui.QRhiTexture.setFormat
        :args:
            :sip:ref:`~PyQt6.QtGui.QRhiTexture.Format`
        :description: QtGui/QRhiTexture-setFormat-f.rst

    .. sip:method:: PyQt6.QtGui.QRhiTexture.setNativeLayout
        :args:
            int
        :description: QtGui/QRhiTexture-setNativeLayout-f.rst

    .. sip:method:: PyQt6.QtGui.QRhiTexture.setPixelSize
        :args:
            :sip:ref:`~PyQt6.QtCore.QSize`
        :description: QtGui/QRhiTexture-setPixelSize-f.rst

    .. sip:method:: PyQt6.QtGui.QRhiTexture.setReadViewFormat
        :args:
            :sip:ref:`~PyQt6.QtGui.QRhiTexture.ViewFormat`
        :description: QtGui/QRhiTexture-setReadViewFormat-f.rst

    .. sip:method:: PyQt6.QtGui.QRhiTexture.setSampleCount
        :args:
            int
        :description: QtGui/QRhiTexture-setSampleCount-f.rst

    .. sip:method:: PyQt6.QtGui.QRhiTexture.setWriteViewFormat
        :args:
            :sip:ref:`~PyQt6.QtGui.QRhiTexture.ViewFormat`
        :description: QtGui/QRhiTexture-setWriteViewFormat-f.rst

    .. sip:method:: PyQt6.QtGui.QRhiTexture.writeViewFormat
        :returns:
            :sip:ref:`~PyQt6.QtGui.QRhiTexture.ViewFormat`
        :description: QtGui/QRhiTexture-writeViewFormat-f.rst
