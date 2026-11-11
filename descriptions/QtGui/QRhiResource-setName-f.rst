.. sip:method-description::
    :status: todo
    :pysig: c70916e782d9742b90f37ccdedc4f900
    :realsig: (const QByteArray&)
    :digest: 26a499991c29fa3fec10113daa472494

Sets a *name* for the object.

This allows getting descriptive names for the native graphics resources visible in graphics debugging tools, such as `RenderDoc <https://renderdoc.org/>`_ and `XCode <https://developer.apple.com/xcode/>`_.

When it comes to naming native objects by relaying the name via the appropriate graphics API, note that the name is ignored when :sip:ref:`~PyQt6.QtGui.QRhi.Feature.DebugMarkers` are not supported, and may, depending on the backend, also be ignored when :sip:ref:`~PyQt6.QtGui.QRhi.Flag.EnableDebugMarkers` is not set.

**Note:** The name may be ignored for objects other than buffers, renderbuffers, and textures, depending on the backend.

**Note:** The name may be modified. For slotted resources, such as a :sip:ref:`~PyQt6.QtGui.QRhiBuffer` backed by multiple native buffers, :sip:ref:`~PyQt6.QtGui.QRhi` will append a suffix to make the underlying native buffers easily distinguishable from each other.

.. seealso:: :sip:ref:`~PyQt6.QtGui.QRhiResource.name`.
