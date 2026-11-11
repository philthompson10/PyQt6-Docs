.. sip:class-description::
    :status: todo
    :brief: Describes the a single color attachment of a render target
    :digest: 97fca226b1476e2be64eb26ba03e6c02

Describes the a single color attachment of a render target.

A color attachment is either a :sip:ref:`~PyQt6.QtGui.QRhiTexture` or a :sip:ref:`~PyQt6.QtGui.QRhiRenderBuffer`. The former, i.e. when texture() is set, is used in most cases. :sip:ref:`~PyQt6.QtGui.QRhiColorAttachment` is commonly used in combination with :sip:ref:`~PyQt6.QtGui.QRhiTextureRenderTargetDescription`.

**Note:** texture() and renderBuffer() cannot be both set (be non-null at the same time).

Setting renderBuffer instead is recommended only when multisampling is needed. Relying on :sip:ref:`~PyQt6.QtGui.QRhi.Feature.MultisampleRenderBuffer` is a better choice than :sip:ref:`~PyQt6.QtGui.QRhi.Feature.MultisampleTexture` in practice since the former is available in more run time configurations (e.g. when running on OpenGL ES 3.0 which has no support for multisample textures, but does support multisample renderbuffers).

When targeting a non-multisample texture, the layer() and level() indicate the targeted layer (face index ``0-5`` for cubemaps) and mip level. For 3D textures layer() specifies the slice (one 2D image within the 3D texture) to render to. For texture arrays layer() is the array index.

When texture() or renderBuffer() is multisample, resolveTexture() can be set optionally. When set, samples are resolved automatically into that (non-multisample) texture at the end of the render pass. When rendering into a multisample renderbuffers, this is the only way to get resolved, non-multisample content out of them. Multisample textures allow sampling in shaders so for them this is just one option.

**Note:** when resolving is enabled, the multisample data may not be written out at all. This means that the multisample texture() must not be used afterwards with shaders for sampling when resolveTexture() is set.

**Note:** This is a RHI API with limited compatibility guarantees, see :sip:ref:`~PyQt6.QtGui.QRhi` for details.

.. seealso:: :sip:ref:`~PyQt6.QtGui.QRhiTextureRenderTargetDescription`.
