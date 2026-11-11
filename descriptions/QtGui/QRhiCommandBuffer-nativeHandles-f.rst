.. sip:method-description::
    :status: todo
    :pysig: a83331fd7a6dfed300489cb51f6cfa3f
    :realsig: ()
    :digest: 312b1741a07c91cd380013f9fd0744ef

Returns a pointer to a backend-specific :sip:ref:`~PyQt6.QtGui.QRhiNativeHandles` subclass, such as :sip:ref:`~PyQt6.QtGui.QRhiVulkanCommandBufferNativeHandles`. The returned value is ``nullptr`` when exposing the underlying native resources is not supported by, or not applicable to, the backend.

.. seealso:: :sip:ref:`~PyQt6.QtGui.QRhiVulkanCommandBufferNativeHandles`, :sip:ref:`~PyQt6.QtGui.QRhiMetalCommandBufferNativeHandles`, :sip:ref:`~PyQt6.QtGui.QRhiCommandBuffer.beginExternal`, :sip:ref:`~PyQt6.QtGui.QRhiCommandBuffer.endExternal`.
