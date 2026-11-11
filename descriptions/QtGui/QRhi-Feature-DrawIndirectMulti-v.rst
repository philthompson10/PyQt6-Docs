.. sip:enum-member-description::
    :status: todo
    :value: 52
    :digest: f39d03cb7a4ed73817517bf4c6352658

Indicates that a drawCount > 1 is natively supported by the backend in :sip:ref:`~PyQt6.QtGui.QRhiCommandBuffer.drawIndirect` and :sip:ref:`~PyQt6.QtGui.QRhiCommandBuffer.drawIndexedIndirect`. Otherwise, multiple draw calls are issued on the CPU by the RHI. In practice this can be expected to be supported on Vulkan 1.1+, OpenGL 4.3+ and D3D12.
