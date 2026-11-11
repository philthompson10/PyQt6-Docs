.. sip:enum-member-description::
    :status: todo
    :value: 50
    :digest: 088b317a099829c39b3e1d372c9a9fe1

Indicates that enabling depth clamping is supported. When reported as unsupported, which will be the case with OpenGL ES, OpenGL versions before 3.2 without the relevant extension present, and Metal on the iOS Simulator, calling QRhiGraphicsPipeline::setDepthClamp() with an argument of ``true`` has no effect.
