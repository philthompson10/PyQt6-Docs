.. sip:method-description::
    :status: todo
    :pysig: c70916e782d9742b90f37ccdedc4f900
    :realsig: (const QByteArray&)
    :digest: dab4e22bd9b7e9c3af48f66c37aecfae

Records a named debug group on the command buffer with the specified *name*. This is shown in graphics debugging tools such as `RenderDoc <https://renderdoc.org/>`_ and `XCode <https://developer.apple.com/xcode/>`_. The end of the grouping is indicated by :sip:ref:`~PyQt6.QtGui.QRhiCommandBuffer.debugMarkEnd`.

**Note:** Ignored when :sip:ref:`~PyQt6.QtGui.QRhi.Feature.DebugMarkers` are not supported or :sip:ref:`~PyQt6.QtGui.QRhi.Flag.EnableDebugMarkers` is not set.

**Note:** Can be called anywhere within the frame, both inside and outside of passes.
