.. sip:method-description::
    :status: todo
    :pysig: 8e36cd233c0d49f2a14fa3f93e50bc3d
    :realsig: (const QRhiShaderResourceBinding&) const
    :digest: ab1f42aa6de2a343bb7a156bb483e339

Returns ``true`` if the layout is compatible with *other*. The layout does not include the actual resource (such as, buffer or texture) and related parameters (such as, offset or size).

For example, ``a`` and ``b`` below are not equal, but are compatible layout-wise:

::

    auto a = QRhiShaderResourceBinding::uniformBuffer(0, QRhiShaderResourceBinding::VertexStage, buffer);
    auto b = QRhiShaderResourceBinding::uniformBuffer(0, QRhiShaderResourceBinding::VertexStage, someOtherBuffer, 256);
