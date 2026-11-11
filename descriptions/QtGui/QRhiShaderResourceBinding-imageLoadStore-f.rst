.. sip:method-description::
    :status: todo
    :pysig: dd0e5bc56615cafa7bfa88db6d0d5158
    :realsig: (int, QRhiShaderResourceBinding::StageFlags, QRhiTexture*, int)
    :digest: 88e7d64898b51d2334ae6427fdfabd05

Returns a shader resource binding for a read/write storage image with the given *binding* number and pipeline *stage*. The image load/store operations will have access to all layers of the specified *level*. (so if the texture is a cubemap, the shader must use imageCube instead of image2D)

**Note:** When *tex* is not null, it must have been created with :sip:ref:`~PyQt6.QtGui.QRhiTexture.Flag.UsedWithLoadStore`.

**Note:** *tex* can be null. It is valid to create a :sip:ref:`~PyQt6.QtGui.QRhiShaderResourceBindings` with unspecified resources, but such an object cannot be used with :sip:ref:`~PyQt6.QtGui.QRhiCommandBuffer.setShaderResources`. It is however suitable for creating pipelines. Such a pipeline must then always be used together with another, layout compatible :sip:ref:`~PyQt6.QtGui.QRhiShaderResourceBindings` with resources present passed to :sip:ref:`~PyQt6.QtGui.QRhiCommandBuffer.setShaderResources`.

**Note:** Image load/store is only available within the compute and fragment stages.
