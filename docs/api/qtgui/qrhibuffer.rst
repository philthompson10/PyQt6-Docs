:orphan:

.. sip:class:: PyQt6.QtGui.QRhiBuffer
    :inherits: :sip:ref:`~PyQt6.QtGui.QRhiResource`
    :description: QtGui/QRhiBuffer-c.rst

    .. sip:enum:: PyQt6.QtGui.QRhiBuffer.Type
        :description: QtGui/QRhiBuffer-Type-e.rst

        .. sip:enum-member:: PyQt6.QtGui.QRhiBuffer.Type.Dynamic
            :description: QtGui/QRhiBuffer-Type-Dynamic-v.rst

        .. sip:enum-member:: PyQt6.QtGui.QRhiBuffer.Type.Immutable
            :description: QtGui/QRhiBuffer-Type-Immutable-v.rst

        .. sip:enum-member:: PyQt6.QtGui.QRhiBuffer.Type.Static
            :description: QtGui/QRhiBuffer-Type-Static-v.rst

    .. sip:enum:: PyQt6.QtGui.QRhiBuffer.UsageFlag
        :description: QtGui/QRhiBuffer-UsageFlag-e.rst

        .. sip:enum-member:: PyQt6.QtGui.QRhiBuffer.UsageFlag.IndexBuffer
            :description: QtGui/QRhiBuffer-UsageFlag-IndexBuffer-v.rst

        .. sip:enum-member:: PyQt6.QtGui.QRhiBuffer.UsageFlag.IndirectBuffer
            :description: QtGui/QRhiBuffer-UsageFlag-IndirectBuffer-v.rst

        .. sip:enum-member:: PyQt6.QtGui.QRhiBuffer.UsageFlag.StorageBuffer
            :description: QtGui/QRhiBuffer-UsageFlag-StorageBuffer-v.rst

        .. sip:enum-member:: PyQt6.QtGui.QRhiBuffer.UsageFlag.UniformBuffer
            :description: QtGui/QRhiBuffer-UsageFlag-UniformBuffer-v.rst

        .. sip:enum-member:: PyQt6.QtGui.QRhiBuffer.UsageFlag.VertexBuffer
            :description: QtGui/QRhiBuffer-UsageFlag-VertexBuffer-v.rst

    .. sip:method:: PyQt6.QtGui.QRhiBuffer.beginFullDynamicBufferUpdateForCurrentFrame
        :returns:
            str
        :description: QtGui/QRhiBuffer-beginFullDynamicBufferUpdateForCurrentFrame-f.rst

    .. sip:method:: PyQt6.QtGui.QRhiBuffer.create
        :returns:
            bool
        :description: QtGui/QRhiBuffer-create-f.rst

    .. sip:method:: PyQt6.QtGui.QRhiBuffer.endFullDynamicBufferUpdateForCurrentFrame
        :description: QtGui/QRhiBuffer-endFullDynamicBufferUpdateForCurrentFrame-f.rst

    .. sip:method:: PyQt6.QtGui.QRhiBuffer.resourceType
        :returns:
            :sip:ref:`~PyQt6.QtGui.QRhiResource.Type`
        :description: QtGui/QRhiBuffer-resourceType-f.rst

    .. sip:method:: PyQt6.QtGui.QRhiBuffer.setSize
        :args:
            int
        :description: QtGui/QRhiBuffer-setSize-f.rst

    .. sip:method:: PyQt6.QtGui.QRhiBuffer.setType
        :args:
            :sip:ref:`~PyQt6.QtGui.QRhiBuffer.Type`
        :description: QtGui/QRhiBuffer-setType-f.rst

    .. sip:method:: PyQt6.QtGui.QRhiBuffer.setUsage
        :args:
            :sip:ref:`~PyQt6.QtGui.QRhiBuffer.UsageFlag`
        :description: QtGui/QRhiBuffer-setUsage-f.rst

    .. sip:method:: PyQt6.QtGui.QRhiBuffer.size
        :returns:
            int
        :description: QtGui/QRhiBuffer-size-f.rst

    .. sip:method:: PyQt6.QtGui.QRhiBuffer.type
        :returns:
            :sip:ref:`~PyQt6.QtGui.QRhiBuffer.Type`
        :description: QtGui/QRhiBuffer-type-f.rst

    .. sip:method:: PyQt6.QtGui.QRhiBuffer.usage
        :returns:
            :sip:ref:`~PyQt6.QtGui.QRhiBuffer.UsageFlag`
        :description: QtGui/QRhiBuffer-usage-f.rst
