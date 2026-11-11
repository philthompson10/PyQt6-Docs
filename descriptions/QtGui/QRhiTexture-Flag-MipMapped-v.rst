.. sip:enum-member-description::
    :status: todo
    :value: 1 << 3
    :digest: 506b050b1e2ff3c012767b7f27e23721

The texture has mipmaps. The appropriate mip count is calculated automatically and can also be retrieved via :sip:ref:`~PyQt6.QtGui.QRhi.mipLevelsForSize`. The images for the mip levels have to be provided in the texture uploaded or generated via :sip:ref:`~PyQt6.QtGui.QRhiResourceUpdateBatch.generateMips`. Multisample textures cannot have mipmaps.
