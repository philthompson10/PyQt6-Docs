.. sip:enum-member-description::
    :status: todo
    :value: 1 << 13
    :digest: 95445cccf56ac22640ff54fec446c39f

The texture is a 1D texture. Such textures can be created by passing a 0 height and depth to :sip:ref:`~PyQt6.QtGui.QRhi.newTexture`. Note that there can be limitations on one dimensional textures depending on the underlying graphics API. For example, rendering to them or using them with mipmap-based filtering may be unsupported. This is indicated by the :sip:ref:`~PyQt6.QtGui.QRhi.Feature.OneDimensionalTextures` and :sip:ref:`~PyQt6.QtGui.QRhi.Feature.OneDimensionalTextureMipmaps` feature flags.
