.. sip:method-description::
    :status: todo
    :pysig: 14d87e4dca09b686c1c46b831d6fc287
    :realsig: (QRhiShaderResourceBindings*, int, const QRhiCommandBuffer::DynamicOffset*)
    :digest: 74d8b125c856eac1b3a55c5c8b7768f8

Records binding a set of shader resources, such as, uniform buffers or textures, that are made visible to one or more shader stages.

*srb* can be null in which case the current graphics or compute pipeline's associated :sip:ref:`~PyQt6.QtGui.QRhiShaderResourceBindings` is used. When *srb* is non-null, it must be :sip:ref:`~PyQt6.QtGui.QRhiShaderResourceBindings.isLayoutCompatible`, meaning the layout (number of bindings, the type and binding number of each binding) must fully match the :sip:ref:`~PyQt6.QtGui.QRhiShaderResourceBindings` that was associated with the pipeline at the time of calling the pipeline's create().

There are cases when a seemingly unnecessary setShaderResources() call is mandatory: when rebuilding a resource referenced from *srb*, for example changing the size of a :sip:ref:`~PyQt6.QtGui.QRhiBuffer` followed by a QRhiBuffer::create(), this is the place where associated native objects (such as descriptor sets in case of Vulkan) are updated to refer to the current native resources that back the :sip:ref:`~PyQt6.QtGui.QRhiBuffer`, :sip:ref:`~PyQt6.QtGui.QRhiTexture`, :sip:ref:`~PyQt6.QtGui.QRhiSampler` objects referenced from *srb*. In this case setShaderResources() must be called even if *srb* is the same as in the last call.

When *srb* is not null, the :sip:ref:`~PyQt6.QtGui.QRhiShaderResourceBindings` object the pipeline was built with in create() is guaranteed to be not accessed in any form. In fact, it does not need to be valid even at this point: destroying the pipeline's associated srb after create() and instead explicitly specifying another, :sip:ref:`~PyQt6.QtGui.QRhiShaderResourceBindings.isLayoutCompatible` one in every setShaderResources() call is valid.

*dynamicOffsets* allows specifying buffer offsets for uniform buffers that were associated with *srb* via :sip:ref:`~PyQt6.QtGui.QRhiShaderResourceBinding.uniformBufferWithDynamicOffset`. This is different from providing the offset in the *srb* itself: dynamic offsets do not require building a new :sip:ref:`~PyQt6.QtGui.QRhiShaderResourceBindings` for every different offset, can avoid writing the underlying descriptors (with backends where applicable), and so they may be more efficient. Each element of *dynamicOffsets* is a ``binding`` - ``offset`` pair. *dynamicOffsetCount* specifies the number of elements in *dynamicOffsets*.

**Note:** All offsets in *dynamicOffsets* must be byte aligned to the value returned from :sip:ref:`~PyQt6.QtGui.QRhi.ubufAlignment`.

**Note:** Some backends may limit the number of supported dynamic offsets. Avoid using a *dynamicOffsetCount* larger than 8.

**Note:** :sip:ref:`~PyQt6.QtGui.QRhi` will optimize out unnecessary invocations within a pass (taking the conditions described above into account), so therefore overoptimizing to avoid calls to this function is not necessary on the applications' side.

**Note:** This function can only be called inside a render or compute pass, meaning between a :sip:ref:`~PyQt6.QtGui.QRhiCommandBuffer.beginPass` and :sip:ref:`~PyQt6.QtGui.QRhiCommandBuffer.endPass`, or :sip:ref:`~PyQt6.QtGui.QRhiCommandBuffer.beginComputePass` and :sip:ref:`~PyQt6.QtGui.QRhiCommandBuffer.endComputePass`.
