.. sip:method-description::
    :status: todo
    :pysig: c3d0c6c4717034b55987c75ea2f1096b
    :realsig: (QRhiRenderBuffer::NativeRenderBuffer)
    :digest: 7f100dc2e0d882de42d9c3c497c20463

Similar to create() except that no new native renderbuffer objects are created. Instead, the native renderbuffer object specified by *src* is used.

This allows importing an existing renderbuffer object (which must belong to the same device or sharing context, depending on the graphics API) from an external graphics engine.

**Note:** This is currently applicable to OpenGL only. This function exists solely to allow importing a renderbuffer object that is bound to some special, external object, such as an EGLImageKHR. Once the application performed the glEGLImageTargetRenderbufferStorageOES call, the renderbuffer object can be passed to this function to create a wrapping :sip:ref:`~PyQt6.QtGui.QRhiRenderBuffer`, which in turn can be passed in as a color attachment to a :sip:ref:`~PyQt6.QtGui.QRhiTextureRenderTarget` to enable rendering to the EGLImage.

**Note:** pixelSize(), sampleCount(), and flags() must still be set correctly. Passing incorrect sizes and other values to :sip:ref:`~PyQt6.QtGui.QRhi.newRenderBuffer` and then following it with a createFrom() expecting that the native renderbuffer object alone is sufficient to deduce such values is **wrong** and will lead to problems.

**Note:** :sip:ref:`~PyQt6.QtGui.QRhiRenderBuffer` does not take ownership of the native object, and destroy() will not release that object.

**Note:** This function is only implemented when the :sip:ref:`~PyQt6.QtGui.QRhi.Feature.RenderBufferImport` feature is reported as :sip:ref:`~PyQt6.QtGui.QRhi.isFeatureSupported`. Otherwise, the function does nothing and the return value is ``false``.

Returns ``true`` when successful, ``false`` when not supported.
