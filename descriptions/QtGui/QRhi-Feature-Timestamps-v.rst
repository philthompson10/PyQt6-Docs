.. sip:enum-member-description::
    :status: todo
    :value: 4
    :digest: e2911032cb2117fed42c92ca0efaaba9

Indicates that command buffer timestamps are supported. Relevant for :sip:ref:`~PyQt6.QtGui.QRhiCommandBuffer.lastCompletedGpuTime`. This can be expected to be supported on Metal, Vulkan, Direct 3D 11 and 12, and OpenGL contexts of version 3.3 or newer. However, with some of these APIs support for timestamp queries is technically optional, and therefore it cannot be guaranteed that this feature is always supported with every implementation of them.
