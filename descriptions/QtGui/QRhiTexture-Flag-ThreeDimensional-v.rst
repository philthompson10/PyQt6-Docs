.. sip:enum-member-description::
    :status: todo
    :value: 1 << 10
    :digest: 9e004835db2e92d651154971a436be48

The texture is a 3D texture. Such textures should be created with the :sip:ref:`~PyQt6.QtGui.QRhi.newTexture` overload taking a depth in addition to width and height. A 3D texture can have mipmaps but cannot be multisample. When rendering into, or uploading data to a 3D texture, the ``layer`` specified in the render target's color attachment or the upload description refers to a single slice in range [0..depth-1]. The underlying graphics API may not support 3D textures at run time. Support is indicated by the :sip:ref:`~PyQt6.QtGui.QRhi.Feature.ThreeDimensionalTextures` feature.
