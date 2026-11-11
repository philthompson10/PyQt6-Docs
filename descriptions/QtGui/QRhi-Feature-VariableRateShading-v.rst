.. sip:enum-member-description::
    :status: todo
    :value: 44
    :digest: 2b17314f1f9355ad4a4a0b6388ceee51

Indicates that per-draw (per-pipeline) variable rate shading is supported. When reported as supported, :sip:ref:`~PyQt6.QtGui.QRhiCommandBuffer.setShadingRate` is functional and has an effect for :sip:ref:`~PyQt6.QtGui.QRhiGraphicsPipeline` objects that declared :sip:ref:`~PyQt6.QtGui.QRhiGraphicsPipeline.Flag.UsesShadingRate` in their flags. Call :sip:ref:`~PyQt6.QtGui.QRhi.supportedShadingRates` to check which rates are supported. (1x1 is always supported, other typical values are 2x2, 1x2, 2x1, 2x4, 4x2, 4x4). This feature can be expected to be supported with Direct 3D 12 and Vulkan, assuming the implementation and GPU used at run time supports VRS. This enum value has been introduced in Qt 6.9.
