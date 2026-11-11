.. sip:class-description::
    :status: todo
    :brief: Vertex, index, or uniform (constant) buffer resource
    :digest: 30d0a79710c66c3a484e1c805a59e1ae

Vertex, index, or uniform (constant) buffer resource.

**Note:** This is a RHI API with limited compatibility guarantees, see :sip:ref:`~PyQt6.QtGui.QRhi` for details.

A :sip:ref:`~PyQt6.QtGui.QRhiBuffer` encapsulates zero, one, or more native buffer objects (such as a ``VkBuffer`` or ``MTLBuffer``). With some graphics APIs and backends certain types of buffers may not use a native buffer object at all (e.g. OpenGL if uniform buffer objects are not used), but this is transparent to the user of the :sip:ref:`~PyQt6.QtGui.QRhiBuffer` API. Similarly, the fact that some types of buffers may use two or three native buffers underneath, in order to allow efficient per-frame content update without stalling the GPU pipeline, is mostly invisible to the applications and libraries.

A :sip:ref:`~PyQt6.QtGui.QRhiBuffer` instance is always created by calling :sip:ref:`~PyQt6.QtGui.QRhi.newBuffer`. This creates no native graphics resources. To do that, call create() after setting the appropriate options, such as the type, usage flags, size, although in most cases these are already set based on the arguments passed to :sip:ref:`~PyQt6.QtGui.QRhi.newBuffer`.

.. _qrhibuffer-example-usage:

Example usage
.............

To create a uniform buffer for a shader where the GLSL uniform block contains a single ``mat4`` member, and update the contents:

::

    QRhiBuffer *ubuf = rhi->newBuffer(QRhiBuffer::Dynamic, QRhiBuffer::UniformBuffer, 64);
    if (!ubuf->create()) { error(); }
    QRhiResourceUpdateBatch *batch = rhi->nextResourceUpdateBatch();
    QMatrix4x4 mvp;
    // ... set up the modelview-projection matrix
    batch->updateDynamicBuffer(ubuf, 0, 64, mvp.constData());
    // ...
    commandBuffer->resourceUpdate(batch); // or, alternatively, pass 'batch' to a beginPass() call

An example of creating a buffer with vertex data:

::

    const float vertices[] = { -1.0f, -1.0f, 1.0f, -1.0f, 0.0f, 1.0f };
    QRhiBuffer *vbuf = rhi->newBuffer(QRhiBuffer::Immutable, QRhiBuffer::VertexBuffer, sizeof(vertices));
    if (!vbuf->create()) { error(); }
    QRhiResourceUpdateBatch *batch = rhi->nextResourceUpdateBatch();
    batch->uploadStaticBuffer(vbuf, vertices);
    // ...
    commandBuffer->resourceUpdate(batch); // or, alternatively, pass 'batch' to a beginPass() call

An index buffer:

::

    static const quint16 indices[] = { 0, 1, 2 };
    QRhiBuffer *ibuf = rhi->newBuffer(QRhiBuffer::Immutable, QRhiBuffer::IndexBuffer, sizeof(indices));
    if (!ibuf->create()) { error(); }
    QRhiResourceUpdateBatch *batch = rhi->nextResourceUpdateBatch();
    batch->uploadStaticBuffer(ibuf, indices);
    // ...
    commandBuffer->resourceUpdate(batch); // or, alternatively, pass 'batch' to a beginPass() call

.. _qrhibuffer-common-patterns:

Common patterns
...............

A call to create() destroys any existing native resources if create() was successfully called before. If those native resources are still in use by an in-flight frame (i.e., there's a chance they are still read by the GPU), the destroying of those resources is deferred automatically. Thus a very common and convenient pattern to safely increase the size of an already initialized buffer is the following. In practice this drops and creates a whole new set of native resources underneath, so it is not necessarily a cheap operation, but is more convenient and still faster than the alternatives, because by not destroying the ``buf`` object itself, all references to it stay valid in other data structures (e.g., in any :sip:ref:`~PyQt6.QtGui.QRhiShaderResourceBinding` the :sip:ref:`~PyQt6.QtGui.QRhiBuffer` is referenced from).

::

    if (buf->size() < newSize) {
        buf->setSize(newSize);
        if (!buf->create()) { error(); }
    }
    // continue using buf, fill it with new data

When working with uniform buffers, it will sometimes be necessary to combine data for multiple draw calls into a single buffer for efficiency reasons. Be aware of the aligment requirements: with some graphics APIs offsets for a uniform buffer must be aligned to 256 bytes. This applies both to :sip:ref:`~PyQt6.QtGui.QRhiShaderResourceBinding` and to the dynamic offsets passed to :sip:ref:`~PyQt6.QtGui.QRhiCommandBuffer.setShaderResources`. Use the :sip:ref:`~PyQt6.QtGui.QRhi.ubufAlignment` and :sip:ref:`~PyQt6.QtGui.QRhi.ubufAligned` functions to create portable code. As an example, the following is an outline for issuing multiple (``N``) draw calls with the same pipeline and geometry, but with a different data in the uniform buffers exposed at binding point 0. This assumes the buffer is exposed via :sip:ref:`~PyQt6.QtGui.QRhiShaderResourceBinding.uniformBufferWithDynamicOffset` which allows passing a QRhiCommandBuffer::DynamicOffset list to :sip:ref:`~PyQt6.QtGui.QRhiCommandBuffer.setShaderResources`.

::

    const int N = 2;
    const int UB_SIZE = 64 + 4; // assuming a uniform block with { mat4 matrix; float opacity; }
    const int ONE_UBUF_SIZE = rhi->ubufAligned(UB_SIZE);
    const int TOTAL_UBUF_SIZE = N * ONE_UBUF_SIZE;
    QRhiBuffer *ubuf = rhi->newBuffer(QRhiBuffer::Dynamic, QRhiBuffer::UniformBuffer, TOTAL_UBUF_SIZE);
    if (!ubuf->create()) { error(); }
    QRhiResourceUpdateBatch *batch = rhi->nextResourceUpdateBatch();
    for (int i = 0; i < N; ++i) {
        batch->updateDynamicBuffer(ubuf, i * ONE_UBUF_SIZE, 64, matrix.constData());
        batch->updateDynamicBuffer(ubuf, i * ONE_UBUF_SIZE + 64, 4, &opacity);
    }
    // ...
    // beginPass(), set pipeline, etc., and then:
    for (int i = 0; i < N; ++i) {
        QRhiCommandBuffer::DynamicOffset dynOfs[] = { { 0, i * ONE_UBUF_SIZE } };
        cb->setShaderResources(srb, 1, dynOfs);
        cb->draw(36);
    }

.. seealso:: :sip:ref:`~PyQt6.QtGui.QRhiResourceUpdateBatch`, :sip:ref:`~PyQt6.QtGui.QRhi`, :sip:ref:`~PyQt6.QtGui.QRhiCommandBuffer`.
