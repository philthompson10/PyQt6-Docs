.. sip:class-description::
    :status: todo
    :brief: Records upload and copy type of operations
    :digest: 70c2d9718fe00e8193e97a6474970068

Records upload and copy type of operations.

With :sip:ref:`~PyQt6.QtGui.QRhi` it is no longer possible to perform copy type of operations at arbitrary times. Instead, all such operations are recorded into batches that are then passed, most commonly, to :sip:ref:`~PyQt6.QtGui.QRhiCommandBuffer.beginPass`. What then happens under the hood is hidden from the application: the underlying implementations can defer and implement these operations in various different ways.

A resource update batch owns no graphics resources and does not perform any actual operations on its own. It should rather be viewed as a command buffer for update, upload, and copy type of commands.

To get an available, empty batch from the pool, call :sip:ref:`~PyQt6.QtGui.QRhi.nextResourceUpdateBatch`.

**Note:** This is a RHI API with limited compatibility guarantees, see :sip:ref:`~PyQt6.QtGui.QRhi` for details.
