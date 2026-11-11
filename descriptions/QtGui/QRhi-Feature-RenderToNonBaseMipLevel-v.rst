.. sip:enum-member-description::
    :status: todo
    :value: 22
    :digest: 78e6337891a09793701fdea63bdc877b

Indicates that specifying a mip level other than 0 is supported when creating a :sip:ref:`~PyQt6.QtGui.QRhiTextureRenderTarget` with a :sip:ref:`~PyQt6.QtGui.QRhiTexture` as its color attachment. When not supported, :sip:ref:`~PyQt6.QtGui.QRhi.create` will fail whenever the target mip level is not zero. In practice this feature will be unsupported with OpenGL ES 2.0.
