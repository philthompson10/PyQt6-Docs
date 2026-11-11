.. sip:enum-member-description::
    :status: todo
    :value: 12
    :digest: 1c735e75de7e37cab7c82d687cbb8f69

Four components, unsigned normalized 10 bit R, G, and B, 2-bit alpha. This is a packed format so native endianness applies. Note that there is no BGR10A2. This is because RGB10A2 maps to DXGI_FORMAT_R10G10B10A2_UNORM with D3D, MTLPixelFormatRGB10A2Unorm with Metal, VK_FORMAT_A2B10G10R10_UNORM_PACK32 with Vulkan, and GL_RGB10_A2/GL_RGB/GL_UNSIGNED_INT_2_10_10_10_REV on OpenGL (ES). This is the only universally supported RGB30 option. The corresponding :sip:ref:`~PyQt6.QtGui.QImage` formats are :sip:ref:`~PyQt6.QtGui.QImage.Format.Format_BGR30` and :sip:ref:`~PyQt6.QtGui.QImage.Format.Format_A2BGR30_Premultiplied`. (32 bits total)
