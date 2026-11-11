.. sip:method-description::
    :status: todo
    :pysig: 7e7ceddd7d5783165e9954a59b1087bf
    :realsig: (QRhiTexture*)
    :digest: ea4b6c93f3ff8c7d7633a708d7d3d2a5

Sets up the shading rate map to use the texture *src* as the image containing the per-tile shading rates.

Returns ``true`` when successful, ``false`` when not supported.

The :sip:ref:`~PyQt6.QtGui.QRhiShadingRateMap` does not take ownership of *src*.

**Note:** This is functional only when the :sip:ref:`~PyQt6.QtGui.QRhi.Feature.VariableRateShadingMapWithTexture` feature is reported as supported. In practice may be supported on Vulkan and Direct 3D 12 when using modern graphics cards. It will never be supported on OpenGL or Metal, for example.

**Note:** *src* must have a format of :sip:ref:`~PyQt6.QtGui.QRhiTexture.Format.R8UI`.

**Note:** *src* must have a width of ``ceil(render_target_pixel_width / (float)tile_width)`` and a height of ``ceil(render_target_pixel_height / (float)tile_height)``. It is up to the application to ensure the size of the texture is as expected, using the above formula, at all times. The tile size can be queried via :sip:ref:`~PyQt6.QtGui.QRhi.resourceLimit` and :sip:ref:`~PyQt6.QtGui.QRhi.ResourceLimit.ShadingRateImageTileSize`.

Each byte (texel) in the texture corresponds to the shading rate value for one tile. 0 indicates 1x1, while a value of 10 indicates 4x4. See `D3D12_SHADING_RATE <https://learn.microsoft.com/en-us/windows/win32/api/d3d12/ne-d3d12-d3d12_shading_rate>`_ for other possible values.
