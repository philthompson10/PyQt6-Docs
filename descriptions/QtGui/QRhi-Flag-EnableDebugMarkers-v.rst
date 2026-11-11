.. sip:enum-member-description::
    :status: todo
    :value: 1 << 0
    :digest: d766e30320710ac32f56577e408996e3

Enables debug marker groups. Without this frame debugging features like making debug groups and custom resource name visible in external GPU debugging tools will not be available and functions like :sip:ref:`~PyQt6.QtGui.QRhiCommandBuffer.debugMarkBegin` will become no-ops. Avoid enabling in production builds as it may involve a small performance impact. Has no effect when the :sip:ref:`~PyQt6.QtGui.QRhi.Feature.DebugMarkers` feature is not reported as supported.
