.. sip:class-description::
    :status: todo
    :brief: An object that wraps a texture or another kind of native 3D API object
    :digest: af917cb59f7a6e8596445267f83fb36b

An object that wraps a texture or another kind of native 3D API object.

**Note:** This is a RHI API with limited compatibility guarantees, see :sip:ref:`~PyQt6.QtGui.QRhi` for details.

For an introduction to Variable Rate Shading (VRS), see `https://learn.microsoft.com/en-us/windows/win32/direct3d12/vrs <https://learn.microsoft.com/en-us/windows/win32/direct3d12/vrs>`_. Qt supports a subset of the VRS features offered by Direct 3D 12 and Vulkan. In addition, Metal's somewhat different mechanism is supported by making it possible to set up a :sip:ref:`~PyQt6.QtGui.QRhiShadingRateMap` with an existing MTLRasterizationRateMap object.
