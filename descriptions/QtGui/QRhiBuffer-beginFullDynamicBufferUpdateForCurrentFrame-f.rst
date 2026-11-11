.. sip:method-description::
    :status: todo
    :pysig: 341be97d9aff90c9978347f66f945b77
    :realsig: ()
    :digest: a54a0f598bfedbb3d62789c3e108f804

Returns a pointer to a memory block with the host visible buffer data.

This is a shortcut for medium-to-large dynamic uniform buffers that have their **entire** contents (or at least all regions that are read by the shaders in the current frame) changed **in every frame** and the :sip:ref:`~PyQt6.QtGui.QRhiResourceUpdateBatch`-based update mechanism is seen too heavy due to the amount of data copying involved.

The call to this function must be eventually followed by a call to endFullDynamicUniformBufferUpdateForCurrentFrame(), before recording any render or compute pass that relies on this buffer.

**Warning:** Updating data via this method is not compatible with :sip:ref:`~PyQt6.QtGui.QRhiResourceUpdateBatch`-based updates and readbacks. Unexpected behavior may occur when attempting to combine the two update models for the same buffer. Similarly, the data updated this direct way may not be visible to :sip:ref:`~PyQt6.QtGui.QRhiResourceUpdateBatch.readBackBuffer`, depending on the backend.

**Warning:** When updating buffer data via this method, the update must be done in every frame, otherwise backends that perform double or triple buffering of resources may end up in unexpected behavior.

**Warning:** Partial updates are not possible with this approach since some backends may choose a strategy where the previous contents of the buffer is lost upon calling this function. Data must be written to all regions that are read by shaders in the frame currently being prepared.

**Warning:** This function can only be called when recording a frame, so between :sip:ref:`~PyQt6.QtGui.QRhi.beginFrame` and :sip:ref:`~PyQt6.QtGui.QRhi.endFrame`.

**Warning:** This function can only be called on Dynamic buffers.
