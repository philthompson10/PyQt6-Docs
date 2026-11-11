.. sip:enum-member-description::
    :status: todo
    :value: 1 << 1
    :digest: 2be26ed2b7a60cb334908749660624cb

Indicates that the contents of the depth texture is to be loaded when starting a render pass, instead clearing. Only applicable when a texture is used as the depth buffer (QRhiTextureRenderTargetDescription::depthTexture() is set) because depth/stencil renderbuffers may not have any physical backing and data may not be written out in the first place.
