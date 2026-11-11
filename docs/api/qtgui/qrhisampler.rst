:orphan:

.. sip:class:: PyQt6.QtGui.QRhiSampler
    :inherits: :sip:ref:`~PyQt6.QtGui.QRhiResource`
    :description: QtGui/QRhiSampler-c.rst

    .. sip:enum:: PyQt6.QtGui.QRhiSampler.AddressMode
        :description: QtGui/QRhiSampler-AddressMode-e.rst

        .. sip:enum-member:: PyQt6.QtGui.QRhiSampler.AddressMode.ClampToEdge
            :description: QtGui/QRhiSampler-AddressMode-ClampToEdge-v.rst

        .. sip:enum-member:: PyQt6.QtGui.QRhiSampler.AddressMode.Mirror
            :description: QtGui/QRhiSampler-AddressMode-Mirror-v.rst

        .. sip:enum-member:: PyQt6.QtGui.QRhiSampler.AddressMode.Repeat
            :description: QtGui/QRhiSampler-AddressMode-Repeat-v.rst

    .. sip:enum:: PyQt6.QtGui.QRhiSampler.CompareOp
        :description: QtGui/QRhiSampler-CompareOp-e.rst

        .. sip:enum-member:: PyQt6.QtGui.QRhiSampler.CompareOp.Always
            :description: QtGui/QRhiSampler-CompareOp-Always-v.rst

        .. sip:enum-member:: PyQt6.QtGui.QRhiSampler.CompareOp.Equal
            :description: QtGui/QRhiSampler-CompareOp-Equal-v.rst

        .. sip:enum-member:: PyQt6.QtGui.QRhiSampler.CompareOp.Greater
            :description: QtGui/QRhiSampler-CompareOp-Greater-v.rst

        .. sip:enum-member:: PyQt6.QtGui.QRhiSampler.CompareOp.GreaterOrEqual
            :description: QtGui/QRhiSampler-CompareOp-GreaterOrEqual-v.rst

        .. sip:enum-member:: PyQt6.QtGui.QRhiSampler.CompareOp.Less
            :description: QtGui/QRhiSampler-CompareOp-Less-v.rst

        .. sip:enum-member:: PyQt6.QtGui.QRhiSampler.CompareOp.LessOrEqual
            :description: QtGui/QRhiSampler-CompareOp-LessOrEqual-v.rst

        .. sip:enum-member:: PyQt6.QtGui.QRhiSampler.CompareOp.Never
            :description: QtGui/QRhiSampler-CompareOp-Never-v.rst

        .. sip:enum-member:: PyQt6.QtGui.QRhiSampler.CompareOp.NotEqual
            :description: QtGui/QRhiSampler-CompareOp-NotEqual-v.rst

    .. sip:enum:: PyQt6.QtGui.QRhiSampler.Filter
        :description: QtGui/QRhiSampler-Filter-e.rst

        .. sip:enum-member:: PyQt6.QtGui.QRhiSampler.Filter.Linear
            :description: QtGui/QRhiSampler-Filter-Linear-v.rst

        .. sip:enum-member:: PyQt6.QtGui.QRhiSampler.Filter.Nearest
            :description: QtGui/QRhiSampler-Filter-Nearest-v.rst

        .. sip:enum-member:: PyQt6.QtGui.QRhiSampler.Filter.None_
            :description: QtGui/QRhiSampler-Filter-None_-v.rst

    .. sip:method:: PyQt6.QtGui.QRhiSampler.addressU
        :returns:
            :sip:ref:`~PyQt6.QtGui.QRhiSampler.AddressMode`
        :description: QtGui/QRhiSampler-addressU-f.rst

    .. sip:method:: PyQt6.QtGui.QRhiSampler.addressV
        :returns:
            :sip:ref:`~PyQt6.QtGui.QRhiSampler.AddressMode`
        :description: QtGui/QRhiSampler-addressV-f.rst

    .. sip:method:: PyQt6.QtGui.QRhiSampler.addressW
        :returns:
            :sip:ref:`~PyQt6.QtGui.QRhiSampler.AddressMode`
        :description: QtGui/QRhiSampler-addressW-f.rst

    .. sip:method:: PyQt6.QtGui.QRhiSampler.create
        :returns:
            bool
        :description: QtGui/QRhiSampler-create-f.rst

    .. sip:method:: PyQt6.QtGui.QRhiSampler.magFilter
        :returns:
            :sip:ref:`~PyQt6.QtGui.QRhiSampler.Filter`
        :description: QtGui/QRhiSampler-magFilter-f.rst

    .. sip:method:: PyQt6.QtGui.QRhiSampler.minFilter
        :returns:
            :sip:ref:`~PyQt6.QtGui.QRhiSampler.Filter`
        :description: QtGui/QRhiSampler-minFilter-f.rst

    .. sip:method:: PyQt6.QtGui.QRhiSampler.mipmapMode
        :returns:
            :sip:ref:`~PyQt6.QtGui.QRhiSampler.Filter`
        :description: QtGui/QRhiSampler-mipmapMode-f.rst

    .. sip:method:: PyQt6.QtGui.QRhiSampler.resourceType
        :returns:
            :sip:ref:`~PyQt6.QtGui.QRhiResource.Type`
        :description: QtGui/QRhiSampler-resourceType-f.rst

    .. sip:method:: PyQt6.QtGui.QRhiSampler.setAddressU
        :args:
            :sip:ref:`~PyQt6.QtGui.QRhiSampler.AddressMode`
        :description: QtGui/QRhiSampler-setAddressU-f.rst

    .. sip:method:: PyQt6.QtGui.QRhiSampler.setAddressV
        :args:
            :sip:ref:`~PyQt6.QtGui.QRhiSampler.AddressMode`
        :description: QtGui/QRhiSampler-setAddressV-f.rst

    .. sip:method:: PyQt6.QtGui.QRhiSampler.setAddressW
        :args:
            :sip:ref:`~PyQt6.QtGui.QRhiSampler.AddressMode`
        :description: QtGui/QRhiSampler-setAddressW-f.rst

    .. sip:method:: PyQt6.QtGui.QRhiSampler.setMagFilter
        :args:
            :sip:ref:`~PyQt6.QtGui.QRhiSampler.Filter`
        :description: QtGui/QRhiSampler-setMagFilter-f.rst

    .. sip:method:: PyQt6.QtGui.QRhiSampler.setMinFilter
        :args:
            :sip:ref:`~PyQt6.QtGui.QRhiSampler.Filter`
        :description: QtGui/QRhiSampler-setMinFilter-f.rst

    .. sip:method:: PyQt6.QtGui.QRhiSampler.setMipmapMode
        :args:
            :sip:ref:`~PyQt6.QtGui.QRhiSampler.Filter`
        :description: QtGui/QRhiSampler-setMipmapMode-f.rst

    .. sip:method:: PyQt6.QtGui.QRhiSampler.setTextureCompareOp
        :args:
            :sip:ref:`~PyQt6.QtGui.QRhiSampler.CompareOp`
        :description: QtGui/QRhiSampler-setTextureCompareOp-f.rst

    .. sip:method:: PyQt6.QtGui.QRhiSampler.textureCompareOp
        :returns:
            :sip:ref:`~PyQt6.QtGui.QRhiSampler.CompareOp`
        :description: QtGui/QRhiSampler-textureCompareOp-f.rst
