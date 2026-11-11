.. sip:method-description::
    :status: todo
    :pysig: d41d8cd98f00b204e9800998ecf8427e
    :realsig: ()
    :digest: ae8aa9023a258fda649bba017804be43

When called without a frame being recorded, this function is equivalent to deleting the object. Between a :sip:ref:`~PyQt6.QtGui.QRhi.beginFrame` and :sip:ref:`~PyQt6.QtGui.QRhi.endFrame` however the behavior is different: the :sip:ref:`~PyQt6.QtGui.QRhiResource` will not be destroyed until the frame is submitted via :sip:ref:`~PyQt6.QtGui.QRhi.endFrame`, thus satisfying the :sip:ref:`~PyQt6.QtGui.QRhi` requirement of not altering :sip:ref:`~PyQt6.QtGui.QRhiResource` objects that are referenced by the frame being recorded.

If the :sip:ref:`~PyQt6.QtGui.QRhi` that created this object is already destroyed, the object is deleted immediately.

Using deleteLater() can be a useful convenience in many cases, and it complements the low-level guarantee (that the underlying native graphics objects are never destroyed until it is safe to do so and it is known for sure that they are not used by the GPU in an still in-flight frame), by offering a way to make sure the C++ object instances (of :sip:ref:`~PyQt6.QtGui.QRhiBuffer`, :sip:ref:`~PyQt6.QtGui.QRhiTexture`, etc.) themselves also stay valid until the end of the current frame.

The following example shows a convenient way of creating a throwaway buffer that is only used in one frame and gets automatically released in endFrame(). (when it comes to the underlying native buffer(s), the usual guarantee applies: the :sip:ref:`~PyQt6.QtGui.QRhi` backend defers the releasing of those until it is guaranteed that the frame in which the buffer is accessed by the GPU has completed)

::

    rhi->beginFrame(swapchain);
    QRhiBuffer *buf = rhi->newBuffer(QRhiBuffer::Immutable, QRhiBuffer::VertexBuffer, 256);
    buf->deleteLater(); // !
    u = rhi->nextResourceUpdateBatch();
    u->uploadStaticBuffer(buf, data);
    // ... draw with buf
    rhi->endFrame();

.. seealso:: :sip:ref:`~PyQt6.QtGui.QRhiResource.destroy`.
