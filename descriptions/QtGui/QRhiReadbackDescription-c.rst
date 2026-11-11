.. sip:class-description::
    :status: todo
    :brief: Describes a readback (reading back texture contents from possibly GPU-only memory) operation
    :digest: cf7e2061c5bbe0f3071ae823b1c0e70d

Describes a readback (reading back texture contents from possibly GPU-only memory) operation.

The source of the readback operation is either a :sip:ref:`~PyQt6.QtGui.QRhiTexture` or the current backbuffer of the currently targeted :sip:ref:`~PyQt6.QtGui.QRhiSwapChain`. When texture() is not set, the swapchain is used. Otherwise the specified :sip:ref:`~PyQt6.QtGui.QRhiTexture` is treated as the source.

**Note:** Textures used in readbacks must be created with :sip:ref:`~PyQt6.QtGui.QRhiTexture.Flag.UsedAsTransferSource`.

**Note:** Swapchains used in readbacks must be created with :sip:ref:`~PyQt6.QtGui.QRhiSwapChain.Flag.UsedAsTransferSource`.

layer() and level() are only applicable when the source is a :sip:ref:`~PyQt6.QtGui.QRhiTexture`.

**Note:** Multisample textures cannot be read back. Readbacks are supported for multisample swapchain buffers however.

**Note:** This is a RHI API with limited compatibility guarantees, see :sip:ref:`~PyQt6.QtGui.QRhi` for details.
