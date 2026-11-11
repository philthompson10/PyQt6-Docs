.. sip:enum-member-description::
    :status: todo
    :value: 15
    :digest: 0a2c66435d86ca0cac6f463929376ebc

The tile size for shading rate textures. 0 if the :sip:ref:`~PyQt6.QtGui.QRhi.Feature.VariableRateShadingMapWithTexture` feature is not supported. Otherwise a value such as 16, indicating, for example, a tile size of 16x16. Each byte in the (R8UI) shading rate texture defines then the shading rate for a tile of 16x16 pixels. See :sip:ref:`~PyQt6.QtGui.QRhiShadingRateMap` for details.
