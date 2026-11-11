.. sip:attribute-description::
    :status: todo
    :digest: 62db1a8521bc4bec1cefee49afce5679

Specifies the **minimum** feature level passed to `D3D12CreateDevice() <https://learn.microsoft.com/en-us/windows/win32/api/d3d12/nf-d3d12-d3d12createdevice>`_. When not set, ``D3D_FEATURE_LEVEL_11_0`` is used. See `this page <https://learn.microsoft.com/en-us/windows/win32/direct3d12/hardware-feature-levels>`_ for details.

Relevant only when :sip:ref:`~PyQt6.QtGui.QRhi` creates the device, ignored when importing a device and device context.
