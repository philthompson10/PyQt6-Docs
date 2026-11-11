.. sip:method-description::
    :status: todo
    :pysig: d41d8cd98f00b204e9800998ecf8427e
    :realsig: ()
    :digest: cebf6bcf1c8b651a2ad9863f32997ae7

To be called when the application before the application is about to enqueue commands to the current pass' command buffer by calling graphics API functions directly.

**Note:** This is only available when the intent was declared upfront in :sip:ref:`~PyQt6.QtGui.QRhiCommandBuffer.beginPass` or :sip:ref:`~PyQt6.QtGui.QRhiCommandBuffer.beginComputePass`. Therefore this function must only be called when the pass recording was started with specifying :sip:ref:`~PyQt6.QtGui.QRhiCommandBuffer.BeginPassFlag.ExternalContent`.

With Vulkan, Metal, or Direct3D 12 one can query the native command buffer or encoder objects via :sip:ref:`~PyQt6.QtGui.QRhiCommandBuffer.nativeHandles` and enqueue commands to them. With OpenGL or Direct3D 11 the (device) context can be retrieved from :sip:ref:`~PyQt6.QtGui.QRhi.nativeHandles`. However, this must never be done without ensuring the :sip:ref:`~PyQt6.QtGui.QRhiCommandBuffer`'s state stays up-to-date. Hence the requirement for wrapping any externally added command recording between beginExternal() and :sip:ref:`~PyQt6.QtGui.QRhiCommandBuffer.endExternal`. Conceptually this is the same as :sip:ref:`~PyQt6.QtGui.QPainter`'s :sip:ref:`~PyQt6.QtGui.QPainter.beginNativePainting` and :sip:ref:`~PyQt6.QtGui.QPainter.endNativePainting` functions.

For OpenGL in particular, this function has an additional task: it makes sure the context is made current on the current thread.

**Note:** Once beginExternal() is called, no other render pass specific functions (``set\*`` or ``draw\*``) must be called on the :sip:ref:`~PyQt6.QtGui.QRhiCommandBuffer` until :sip:ref:`~PyQt6.QtGui.QRhiCommandBuffer.endExternal`.

**Warning:** Some backends may return a native command buffer object from :sip:ref:`~PyQt6.QtGui.QRhiCommandBuffer.nativeHandles` that is different from the primary one when inside a beginExternal() - :sip:ref:`~PyQt6.QtGui.QRhiCommandBuffer.endExternal` block. Therefore it is important to (re)query the native command buffer object after calling beginExternal(). In practical terms this means that with Vulkan for example the externally recorded Vulkan commands are placed onto a secondary command buffer (with VK_COMMAND_BUFFER_USAGE_RENDER_PASS_CONTINUE_BIT). :sip:ref:`~PyQt6.QtGui.QRhiCommandBuffer.nativeHandles` returns this secondary command buffer when called between begin/\ :sip:ref:`~PyQt6.QtGui.QRhiCommandBuffer.endExternal`.

.. seealso:: :sip:ref:`~PyQt6.QtGui.QRhiCommandBuffer.endExternal`, :sip:ref:`~PyQt6.QtGui.QRhiCommandBuffer.nativeHandles`.
