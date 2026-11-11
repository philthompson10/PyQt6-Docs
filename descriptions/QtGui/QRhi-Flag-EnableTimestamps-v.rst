.. sip:enum-member-description::
    :status: todo
    :value: 1 << 3
    :digest: 4d86038d741730785f50b44ba0fb6e29

Enables GPU timestamp collection. When not set, :sip:ref:`~PyQt6.QtGui.QRhiCommandBuffer.lastCompletedGpuTime` always returns 0. Enable this only when needed since there may be a small amount of extra work involved (e.g. timestamp queries), depending on the underlying graphics API. Has no effect when the :sip:ref:`~PyQt6.QtGui.QRhi.Feature.Timestamps` feature is not reported as supported.
