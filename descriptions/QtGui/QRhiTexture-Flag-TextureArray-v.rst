.. sip:enum-member-description::
    :status: todo
    :value: 1 << 12
    :digest: ff471a08aee3b04931df7dc83c21702d

The texture is a texture array, i.e. a single texture object that is a homogeneous array of 2D textures. Texture arrays are created with :sip:ref:`~PyQt6.QtGui.QRhi.newTextureArray`. The underlying graphics API may not support texture array objects at run time. Support is indicated by the :sip:ref:`~PyQt6.QtGui.QRhi.Feature.TextureArrays` feature. When rendering into, or uploading data to a texture array, the ``layer`` specified in the render target's color attachment or the upload description selects a single element in the array.
