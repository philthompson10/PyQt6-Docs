.. sip:class-description::
    :status: todo
    :brief: Describes a texture-to-texture copy operation
    :digest: c1adf29c47788433a65df160b86fa11e

Describes a texture-to-texture copy operation.

An empty pixelSize() indicates that the entire subresource is to be copied. A default constructed copy description therefore leads to copying the entire subresource at level 0 of layer 0.

**Note:** The source texture must be created with :sip:ref:`~PyQt6.QtGui.QRhiTexture.Flag.UsedAsTransferSource`.

**Note:** The source and destination rectangles defined by pixelSize(), sourceTopLeft(), and destinationTopLeft() must fit the source and destination textures, respectively. The behavior is undefined otherwise.

With cubemaps, 3D textures, and texture arrays one face or slice can be copied at a time. The face or slice is specified by the source and destination layer indices. With mipmapped textures one mip level can be copied at a time. The source and destination layer and mip level indices can differ, but the size and position must be carefully controlled to avoid out of bounds copies, in which case the behavior is undefined.

**Note:** This is a RHI API with limited compatibility guarantees, see :sip:ref:`~PyQt6.QtGui.QRhi` for details.
