.. sip:enum-member-description::
    :status: todo
    :value: 0x851b
    :realname: Qt3DRender::QAbstractTexture::CubeMapFace::AllFaces
    :digest: 1ec1212371e716b032f4c6d198b66ff4

Specify all the faces of a cube map

**Note:** AllFaces should only be used when a behavior needs to be applied to all the faces of a cubemap. This is the case for example when using a cube map as a texture attachment. Using AllFaces in the attachment specfication would result in all faces being bound to the attachment point. On the other hand, if a specific face is specified, the attachment would only be using the specified face.
