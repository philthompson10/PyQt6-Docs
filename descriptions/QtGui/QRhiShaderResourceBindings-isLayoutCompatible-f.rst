.. sip:method-description::
    :status: todo
    :pysig: c563fc3d0c47dff53109966f69b6d3ff
    :realsig: (const QRhiShaderResourceBindings*) const
    :digest: 0a69900b006500169d1fa914fc13e3ba

Returns ``true`` if the layout is compatible with *other*. The layout does not include the actual resource (such as, buffer or texture) and related parameters (such as, offset or size). It does include the binding point, pipeline stage, and resource type, however. The number and order of the bindings must also match in order to be compatible.

When there is a :sip:ref:`~PyQt6.QtGui.QRhiGraphicsPipeline` created with this :sip:ref:`~PyQt6.QtGui.QRhiShaderResourceBindings`, and the function returns ``true``, *other* can then safely be passed to :sip:ref:`~PyQt6.QtGui.QRhiCommandBuffer.setShaderResources`, and so be used with the pipeline in place of this :sip:ref:`~PyQt6.QtGui.QRhiShaderResourceBindings`.

**Note:** This function must only be called after a successful create(), because it relies on data generated during the baking of the underlying data structures. This way the function can implement a comparison approach that is more efficient than iterating through two binding lists and calling :sip:ref:`~PyQt6.QtGui.QRhiShaderResourceBinding.isLayoutCompatible` on each pair. This becomes relevant especially when this function is called at a high frequency.

.. seealso:: :sip:ref:`~PyQt6.QtGui.QRhiShaderResourceBindings.serializedLayoutDescription`.
