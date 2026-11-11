.. sip:enum-member-description::
    :status: todo
    :value: 1 << 0
    :digest: 01bff67661728a6bfa2f76950d9584f2

Indicates that the target surface has transparency with premultiplied alpha. For example, this is what Qt Quick uses when the alpha channel is enabled on the target :sip:ref:`~PyQt6.QtGui.QWindow`, because the scenegraph rendrerer always outputs fragments with alpha multiplied into the red, green, and blue values. To ensure identical behavior across platforms, always set :sip:ref:`~PyQt6.QtGui.QSurfaceFormat.alphaBufferSize` to a non-zero value on the target :sip:ref:`~PyQt6.QtGui.QWindow` whenever this flag is set on the swapchain.
