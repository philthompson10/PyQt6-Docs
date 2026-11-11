.. sip:method-description::
    :status: todo
    :pysig: dd0e5bc56615cafa7bfa88db6d0d5158
    :realsig: (int, QRhiShaderResourceBinding::StageFlags, QRhiTexture*, int)
    :digest: 798cefaaa36ef3a2d6ce18fabf08fa2f

Returns a shader resource binding for a read-only storage image with the given *binding* number and pipeline *stage*. The image load operations will have access to all layers of the specified *level*. (so if the texture is a cubemap, the shader must use imageCube instead of image2D)

**Note:** When *tex* is not null, it must have been created with :sip:ref:`~PyQt6.QtGui.QRhiTexture.Flag.UsedWithLoadStore`.

**Note:** *tex* can be null. It is valid to create a :sip:ref:`~PyQt6.QtGui.QRhiShaderResourceBindings` with unspecified resources, but such an object cannot be used with :sip:ref:`~PyQt6.QtGui.QRhiCommandBuffer.setShaderResources`. It is however suitable for creating pipelines. Such a pipeline must then always be used together with another, layout compatible :sip:ref:`~PyQt6.QtGui.QRhiShaderResourceBindings` with resources present passed to :sip:ref:`~PyQt6.QtGui.QRhiCommandBuffer.setShaderResources`.

**Note:** Image load/store is only available within the compute and fragment stages.
