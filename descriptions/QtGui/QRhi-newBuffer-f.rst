.. sip:method-description::
    :status: todo
    :pysig: 788c20f47af174d5d14a95b2e8686038
    :realsig: (QRhiBuffer::Type, QRhiBuffer::UsageFlags, quint32)
    :digest: 9204b565b492ab3ac2a203fbca1b14bf

Returns a new buffer with the specified *type*, *usage*, and *size*.

**Note:** Some *usage* and *type* combinations may not be supported by all backends. See :sip:ref:`~PyQt6.QtGui.QRhiBuffer.UsageFlag` and :sip:ref:`~PyQt6.QtGui.QRhi.Feature.NonDynamicUniformBuffers`.

**Note:** Backends may choose to allocate buffers bigger than *size*. This is done transparently to applications, so there are no special restrictions on the value of *size*. QRhiBuffer::size() will always report back the value that was requested in *size*.

.. seealso:: :sip:ref:`~PyQt6.QtGui.QRhiResource.destroy`.
