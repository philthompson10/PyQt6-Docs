.. sip:method-description::
    :status: todo
    :pysig: d41d8cd98f00b204e9800998ecf8427e
    :realsig: ()
    :digest: b5c357a91fb93840bfeb25e3b6e57d09

To be called once the externally added commands are recorded to the command buffer or context.

**Note:** All :sip:ref:`~PyQt6.QtGui.QRhiCommandBuffer` state must be assumed as invalid after calling this function. Pipelines, vertex and index buffers, and other state must be set again if more draw calls are recorded after the external commands.

.. seealso:: :sip:ref:`~PyQt6.QtGui.QRhiCommandBuffer.beginExternal`, :sip:ref:`~PyQt6.QtGui.QRhiCommandBuffer.nativeHandles`.
