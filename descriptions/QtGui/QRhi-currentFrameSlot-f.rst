.. sip:method-description::
    :status: todo
    :pysig: fa7153f7ed1cb6c0fcf2ffb2fac21748
    :realsig: () const
    :digest: cb9acdfde829f077d0434b1622e7f977

Returns the current frame slot index while recording a frame. Unspecified when called outside an active frame (that is, when :sip:ref:`~PyQt6.QtGui.QRhi.isRecordingFrame` is ``false``).

With backends like Vulkan or Metal, it is the responsibility of the :sip:ref:`~PyQt6.QtGui.QRhi` backend to block whenever starting a new frame and finding the CPU is already ``FramesInFlight - 1`` frames ahead of the GPU (because the command buffer submitted in frame no. ``current`` - ``FramesInFlight`` has not yet completed).

Resources that tend to change between frames (such as, the native buffer object backing a :sip:ref:`~PyQt6.QtGui.QRhiBuffer` with type :sip:ref:`~PyQt6.QtGui.QRhiBuffer.Type.Dynamic`) exist in multiple versions, so that each frame, that can be submitted while a previous one is still being processed, works with its own copy, thus avoiding the need to stall the pipeline when preparing the frame. (The contents of a resource that may still be in use in the GPU should not be touched, but simply always waiting for the previous frame to finish would reduce GPU utilization and ultimately, performance and efficiency.)

Conceptually this is somewhat similar to copy-on-write schemes used by some C++ containers and other types. It may also be similar to what an OpenGL or Direct 3D 11 implementation performs internally for certain type of objects.

In practice, such double (or triple) buffering resources is realized in the Vulkan, Metal, and similar :sip:ref:`~PyQt6.QtGui.QRhi` backends by having a fixed number of native resource (such as, VkBuffer) ``slots`` behind a :sip:ref:`~PyQt6.QtGui.QRhiResource`. That can then be indexed by a frame slot index running 0, 1, .., :sip:ref:`~PyQt6.QtGui.QRhi.ResourceLimit.FramesInFlight`-1, and then wrapping around.

All this is managed transparently to the users of :sip:ref:`~PyQt6.QtGui.QRhi`. However, applications that integrate rendering done directly with the graphics API may want to perform a similar double or triple buffering of their own graphics resources. That is then most easily achieved by knowing the values of the maximum number of in-flight frames (retrievable via :sip:ref:`~PyQt6.QtGui.QRhi.resourceLimit`) and the current frame (slot) index (returned by this function).

.. seealso:: :sip:ref:`~PyQt6.QtGui.QRhi.isRecordingFrame`, :sip:ref:`~PyQt6.QtGui.QRhi.beginFrame`, :sip:ref:`~PyQt6.QtGui.QRhi.endFrame`.
