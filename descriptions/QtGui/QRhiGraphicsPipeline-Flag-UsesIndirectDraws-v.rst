.. sip:enum-member-description::
    :status: todo
    :value: 1 << 5
    :digest: db5a3afa40d1f42809343955b160c700

Indicates that this pipeline will be used with indirect draw calls (\ :sip:ref:`~PyQt6.QtGui.QRhiCommandBuffer.drawIndirect` or :sip:ref:`~PyQt6.QtGui.QRhiCommandBuffer.drawIndexedIndirect`). Setting this flag allows the Metal backend to use Indirect Command Buffers (ICB) for GPU-driven rendering, which significantly reduces CPU overhead for large draw counts. Not setting this flag when using indirect draws is still functional but may result in less optimal performance on Metal. This flag has no effect on other backends.
