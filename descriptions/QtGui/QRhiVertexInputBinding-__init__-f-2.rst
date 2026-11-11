.. sip:method-description::
    :status: todo
    :pysig: c6e46f201e2e8d270892c6fdc5067cb5
    :realsig: (quint32, QRhiVertexInputBinding::Classification, quint32)
    :digest: 58ad6ffea830efc9359dc253e2f3c639

Constructs a vertex input binding description with the specified *stride*, classification *cls*, and instance step rate *stepRate*.

**Note:** *stepRate* other than 1 is only supported when :sip:ref:`~PyQt6.QtGui.QRhi.Feature.CustomInstanceStepRate` is reported to be supported.
