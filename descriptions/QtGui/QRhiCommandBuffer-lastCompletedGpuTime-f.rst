.. sip:method-description::
    :status: todo
    :pysig: 546ade640b6edfbc8a086ef31347e768
    :realsig: ()
    :digest: 8ca8ec55ea606b1a93cbbb99564d0063

Returns the last available timestamp, in seconds, when :sip:ref:`~PyQt6.QtGui.QRhi.Flag.EnableTimestamps` was enabled when creating the :sip:ref:`~PyQt6.QtGui.QRhi`. The value indicates the elapsed time on the GPU during the last completed frame.

**Note:** Do not expect results other than 0 when the :sip:ref:`~PyQt6.QtGui.QRhi.Feature.Timestamps` feature is not reported as supported, or when :sip:ref:`~PyQt6.QtGui.QRhi.Flag.EnableTimestamps` was not passed to :sip:ref:`~PyQt6.QtGui.QRhi.create`. There are exceptions to this, because with some graphics APIs (Metal) timings are available without having to perform extra operations (timestamp queries), but portable applications should always consciously opt-in to timestamp collection when they know it is needed, and call this function accordingly.

Care must be exercised with the interpretation of the value, as its precision and granularity is often not controlled by Qt, and depends on the underlying graphics API and its implementation. In particular, comparing the values between different graphics APIs and hardware is discouraged and may be meaningless.

The timing values will likely become available asynchronously. The returned value may therefore be 0 (e.g., for the first 1-2 frames) or the last known value referring to some previous frame. The value my also become 0 again under certain conditions, such as when resizing the window. It can be expected that the most up-to-date available value is retrieved in beginFrame() and becomes queriable via this function once beginFrame() returns.

**Note:** Do not assume that the value refers to the previous (``currently_recorded - 1``) frame. It may refer to ``currently_recorded - 2`` or ``currently_recorded - 3`` as well. The exact behavior may depend on the graphics API and its implementation.

Watch out for the consequences of GPU frequency scaling and GPU clock changes, depending on the platform. For example, on Windows the returned timing may vary in a quite wide range between frames with modern graphics cards, even when submitting frames with a similar, or the same workload. This is out of scope for Qt to control and solve, generally speaking. However, the D3D12 backend automatically calls `ID3D12Device::SetStablePowerState() <https://learn.microsoft.com/en-us/windows/win32/api/d3d12/nf-d3d12-id3d12device-setstablepowerstate>`_ whenever the environment variable ``QT_D3D_STABLE_POWER_STATE`` is set to a non-zero value. This can greatly stabilize the result. It can also have a non-insignificant effect on the CPU-side timings measured via :sip:ref:`~PyQt6.QtCore.QElapsedTimer` for example, especially when offscreen frames are involved.

**Note:** Do not and never ship applications to production with ``QT_D3D_STABLE_POWER_STATE`` set. See the Windows API documentation for details.

.. seealso:: :sip:ref:`~PyQt6.QtGui.QRhi.Feature.Timestamps`, :sip:ref:`~PyQt6.QtGui.QRhi.Flag.EnableTimestamps`.
