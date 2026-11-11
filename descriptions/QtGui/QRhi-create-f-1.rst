.. sip:method-description::
    :status: todo
    :pysig: 92fba857f71b8b7858125f67c5acdc0f
    :realsig: (QRhi::Implementation, QRhiInitParams*, QRhi::Flags, QRhiNativeHandles*, QRhiAdapter*)
    :digest: 7925823f11dbce328bd17cf7c20fcc4c

Returns a new :sip:ref:`~PyQt6.QtGui.QRhi` instance with a backend for the graphics API specified by *impl* with the specified *flags*. Returns ``nullptr`` if the function fails.

*params* must point to an instance of one of the backend-specific subclasses of :sip:ref:`~PyQt6.QtGui.QRhiInitParams`, such as, :sip:ref:`~PyQt6.QtGui.QRhiVulkanInitParams`, :sip:ref:`~PyQt6.QtGui.QRhiMetalInitParams`, :sip:ref:`~PyQt6.QtGui.QRhiD3D11InitParams`, :sip:ref:`~PyQt6.QtGui.QRhiD3D12InitParams`, :sip:ref:`~PyQt6.QtGui.QRhiGles2InitParams`. See these classes for examples on creating a :sip:ref:`~PyQt6.QtGui.QRhi`.

:sip:ref:`~PyQt6.QtGui.QRhi` by design does not implement any fallback logic: if the specified API cannot be initialized, create() will fail, with warnings printed on the debug output by the backends. The clients of :sip:ref:`~PyQt6.QtGui.QRhi`, for example Qt Quick, may however provide additional logic that allow falling back to an API different than what was requested, depending on the platform. If the intention is just to test if initialization would succeed when calling create() at later point, it is preferable to use :sip:ref:`~PyQt6.QtGui.QRhi.probe` instead of create(), because with some backends probing can be implemented in a more lightweight manner as opposed to create(), which performs full initialization of the infrastructure and is wasteful if that :sip:ref:`~PyQt6.QtGui.QRhi` instance is then thrown immediately away.

*importDevice* allows using an already existing graphics device, without :sip:ref:`~PyQt6.QtGui.QRhi` creating its own. When not null, this parameter must point to an instance of one of the subclasses of :sip:ref:`~PyQt6.QtGui.QRhiNativeHandles`: :sip:ref:`~PyQt6.QtGui.QRhiVulkanNativeHandles`, :sip:ref:`~PyQt6.QtGui.QRhiD3D11NativeHandles`, :sip:ref:`~PyQt6.QtGui.QRhiD3D12NativeHandles`, :sip:ref:`~PyQt6.QtGui.QRhiMetalNativeHandles`, :sip:ref:`~PyQt6.QtGui.QRhiGles2NativeHandles`. The exact details and semantics depend on the backand and the underlying graphics API.

Specifying a :sip:ref:`~PyQt6.QtGui.QRhiAdapter` in *adapter* offers a transparent, cross-API alternative to passing in a ``VkPhysicalDevice`` via :sip:ref:`~PyQt6.QtGui.QRhiVulkanNativeHandles`, or an adapter LUID via :sip:ref:`~PyQt6.QtGui.QRhiD3D12NativeHandles`. The ownership of *adapter* is not taken. See :sip:ref:`~PyQt6.QtGui.QRhi.enumerateAdapters` for more information on this approach.

**Note:** *importDevice* and *adapter* cannot be both specified.

.. seealso:: :sip:ref:`~PyQt6.QtGui.QRhi.probe`.
