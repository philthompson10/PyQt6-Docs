.. sip:method-description::
    :status: todo
    :pysig: 53408a6abe02c79d3beb359bed3acd1e
    :realsig: (QRhiShadingRateMap::NativeShadingRateMap)
    :digest: 8a92299dd6f3a0f41c34ad9612a57319

Sets up the shading rate map to use a native 3D API shading rate object *src*.

Returns ``true`` when successful, ``false`` when not supported.

**Note:** This is functional only when the :sip:ref:`~PyQt6.QtGui.QRhi.Feature.VariableRateShadingMap` feature is reported as supported, while :sip:ref:`~PyQt6.QtGui.QRhi.Feature.VariableRateShadingMapWithTexture` feature is not. Currently this is true for Metal, assuming variable rate shading is supported by the GPU.

**Note:** With Metal, the ``object`` field of *src* is expected to contain an id<MTLRasterizationRateMap>. Note that Qt does not perform anything else apart from passing the MTLRasterizationRateMap on to the MTLRenderPassDescriptor. If any special scaling is required, it is up to the application (or the XR compositor) to perform that.
