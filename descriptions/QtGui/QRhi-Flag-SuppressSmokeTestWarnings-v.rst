.. sip:enum-member-description::
    :status: todo
    :value: 1 << 4
    :digest: 5d96dc886b36a5212618c569607082d9

Indicates that, with backends where this is relevant, certain, non-fatal :sip:ref:`~PyQt6.QtGui.QRhi.create` failures should not produce :sip:ref:`~PyQt6.QtCore.qWarning` calls. For example, with D3D11, passing this flag makes a number of warning messages (that appear due to :sip:ref:`~PyQt6.QtGui.QRhi.create` failing) to become categorized debug prints instead under the commonly used ``qt.rhi.general`` logging category. This can be used by engines, such as Qt Quick, that feature fallback logic, i.e. they retry calling :sip:ref:`~PyQt6.QtGui.QRhi.create` with a different set of flags (such as, PreferSoftwareRenderer), in order to hide the unconditional warnings from the output that would be printed when the first :sip:ref:`~PyQt6.QtGui.QRhi.create` attempt had failed.
