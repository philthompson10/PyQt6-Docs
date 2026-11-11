.. sip:method-description::
    :status: todo
    :pysig: a83331fd7a6dfed300489cb51f6cfa3f
    :realsig: ()
    :digest: 51431c0483c58bd7208b69c665ea7071

Returns a pointer to the backend-specific collection of native objects for the device, context, and similar concepts used by the backend.

Cast to :sip:ref:`~PyQt6.QtGui.QRhiVulkanNativeHandles`, :sip:ref:`~PyQt6.QtGui.QRhiD3D11NativeHandles`, :sip:ref:`~PyQt6.QtGui.QRhiD3D12NativeHandles`, :sip:ref:`~PyQt6.QtGui.QRhiGles2NativeHandles`, or :sip:ref:`~PyQt6.QtGui.QRhiMetalNativeHandles` as appropriate.

**Note:** No ownership is transferred, neither for the returned pointer nor for any native objects.
