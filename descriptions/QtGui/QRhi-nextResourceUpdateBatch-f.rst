.. sip:method-description::
    :status: todo
    :pysig: 7e42f4080e1ed0b2e41b452b4fdbaba3
    :realsig: ()
    :digest: 5e2de29318a9e5d70b9787df2c4fc34e

Returns an available, empty batch to which copy type of operations can be recorded.

**Note:** the return value is not owned by the caller and must never be destroyed. Instead, the batch is returned the pool for reuse by passing it to :sip:ref:`~PyQt6.QtGui.QRhiCommandBuffer.beginPass`, :sip:ref:`~PyQt6.QtGui.QRhiCommandBuffer.endPass`, or :sip:ref:`~PyQt6.QtGui.QRhiCommandBuffer.resourceUpdate`, or by calling :sip:ref:`~PyQt6.QtGui.QRhiResourceUpdateBatch.release` on it.

**Note:** Can be called outside :sip:ref:`~PyQt6.QtGui.QRhi.beginFrame` - :sip:ref:`~PyQt6.QtGui.QRhi.endFrame` as well since a batch instance just collects data on its own, it does not perform any operations.

Due to not being tied to a frame being recorded, the following sequence is valid for example:

::

    rhi->beginFrame(swapchain);
    QRhiResourceUpdateBatch *u = rhi->nextResourceUpdateBatch();
    u->uploadStaticBuffer(buf, data);
    // ... do not commit the batch
    rhi->endFrame();
    // u stays valid (assuming buf stays valid as well)
    rhi->beginFrame(swapchain);
    swapchain->currentFrameCommandBuffer()->resourceUpdate(u);
    // ... draw with buf
    rhi->endFrame();

**Warning:** The maximum number of batches per :sip:ref:`~PyQt6.QtGui.QRhi` is 64. When this limit is reached, the function will return null until a batch is returned to the pool.
