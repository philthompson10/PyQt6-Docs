.. sip:method-description::
    :status: todo
    :pysig: 364191bc772363d61cf96ad3eac70cf9
    :realsig: (const QSize&)
    :digest: 3533711732395551aa6a751998a9fa70

Sets the shading rate for the following draw calls to *coarsePixelSize*.

The default is 1x1.

Functional only when the :sip:ref:`~PyQt6.QtGui.QRhi.Feature.VariableRateShading` feature is reported as supported and the :sip:ref:`~PyQt6.QtGui.QRhiGraphicsPipeline`\ (s) bound on the command buffer were declaring :sip:ref:`~PyQt6.QtGui.QRhiGraphicsPipeline.Flag.UsesShadingRate` when creating them.

Call :sip:ref:`~PyQt6.QtGui.QRhi.supportedShadingRates` to check what shading rates are supported for a given sample count.

When both a :sip:ref:`~PyQt6.QtGui.QRhiShadingRateMap` and this function are in use, the higher of the two shading rates is used for each tile. There is currently no control offered over the combiner behavior.
