.. sip:class-description::
    :status: todo
    :brief: Renderbuffer resource
    :digest: c88bdd7bb34110eb3369425f3ef4da44

Renderbuffer resource.

Renderbuffers cannot be sampled or read but have some benefits over textures in some cases:

A :sip:ref:`~PyQt6.QtGui.QRhiRenderBuffer.Type.DepthStencil` renderbuffer may be lazily allocated and be backed by transient memory with some APIs. On some platforms this may mean the depth/stencil buffer uses no physical backing at all.

That transient nature has a consequence: the contents of a :sip:ref:`~PyQt6.QtGui.QRhiRenderBuffer.Type.DepthStencil` renderbuffer are not guaranteed to survive if a backend has to interrupt and restart a render pass internally. With Metal this happens when a draw call is implemented via indirect command buffers, which is the case for a high draw count :sip:ref:`~PyQt6.QtGui.QRhiCommandBuffer.drawIndexedIndirect`, and also when tessellation is used. Draws recorded after such a call then depth-test against a depth buffer that lost its contents. When this matters, attach a depth or depth-stencil :sip:ref:`~PyQt6.QtGui.QRhiTexture` with setDepthTexture() instead of a renderbuffer: that is preserved across an interruption, unless :sip:ref:`~PyQt6.QtGui.QRhiTextureRenderTarget.Flag.DoNotStoreDepthStencilContents` is set.

:sip:ref:`~PyQt6.QtGui.QRhiRenderBuffer.Type.Color` renderbuffers are useful since :sip:ref:`~PyQt6.QtGui.QRhi.Feature.MultisampleRenderBuffer` may be supported even when :sip:ref:`~PyQt6.QtGui.QRhi.Feature.MultisampleTexture` is not.

How the renderbuffer is implemented by a backend is not exposed to the applications. In some cases it may be backed by ordinary textures, while in others there may be a different kind of native resource used.

Renderbuffers that are used as (and are only used as) depth-stencil buffers in combination with a :sip:ref:`~PyQt6.QtGui.QRhiSwapChain`'s color buffers should have the :sip:ref:`~PyQt6.QtGui.QRhiRenderBuffer.Flag.UsedWithSwapChainOnly` flag set. This serves a double purpose: such buffers, depending on the backend and the underlying APIs, be more efficient, and :sip:ref:`~PyQt6.QtGui.QRhi` provides automatic sizing behavior to match the color buffers, which means calling setPixelSize() and create() are not necessary for such renderbuffers.

**Note:** This is a RHI API with limited compatibility guarantees, see :sip:ref:`~PyQt6.QtGui.QRhi` for details.
