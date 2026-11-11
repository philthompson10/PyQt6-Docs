.. sip:method-description::
    :status: todo
    :pysig: be31aa07c9c9562f9d1ccdcdaa33fd6b
    :realsig: (QRhi::Implementation, QRhiInitParams*, QRhiNativeHandles*)
    :digest: f3b91e88e556b9696c91501b79f28f46

Returns the list of adapters (physical devices) present, or an empty list when such control is not available with a given graphics API.

Backends where such level of control is not available, the returned list is always empty. Thus an empty list does not indicate there are no graphics devices in the system, but that fine-grained control over selecting which one to use is not available.

Backends for Direct 3D 11, Direct 3D 12, and Vulkan can be expected to fully support enumerating adapters. Others may not. The backend is specified by *impl*. A :sip:ref:`~PyQt6.QtGui.QRhiAdapter` returned from this function must only be used in a :sip:ref:`~PyQt6.QtGui.QRhi.create` call with the same *impl*. Some underlying APIs may present further limitations, with Vulkan in particular the :sip:ref:`~PyQt6.QtGui.QRhiAdapter` is specified to the :sip:ref:`~PyQt6.QtGui.QVulkanInstance` (``VkInstance``).

The caller is expected to destroy the :sip:ref:`~PyQt6.QtGui.QRhiAdapter` objects in the list. Apart from querying info(), the only purpose of these objects is to be passed on to :sip:ref:`~PyQt6.QtGui.QRhi.create`, or the corresponding functions in higher layers such as Qt Quick.

The following snippet, written specifically for Vulkan, shows how to enumerate the available physical devices and request to create a :sip:ref:`~PyQt6.QtGui.QRhi` for the chosen one. This in practice is equivalent to passing in a ``VkPhysicalDevice`` via a :sip:ref:`~PyQt6.QtGui.QRhiVulkanNativeHandles` to :sip:ref:`~PyQt6.QtGui.QRhi.create`, but it involves less API-specific code on the application side:

::

    QRhiVulkanInitParams initParams;
    initParams.inst = &vulkanInstance;
    QRhi::AdapterList adapters = QRhi::enumerateAdapters(QRhi::Vulkan, &initParams);
    QRhiAdapter *chosenAdapter = nullptr;
    for (QRhiAdapter *adapter : adapters) {
        if (looksGood(adapter->info())) {
            chosenAdapter = adapter;
            break;
        }
    }
    QRhi *rhi = QRhi::create(QRhi::Vulkan, &initParams, {}, nullptr, chosenAdapter);
    qDeleteAll(adapters);

Passing in *params* is required due to some of the underlying graphics APIs' design. With Vulkan in particular, the :sip:ref:`~PyQt6.QtGui.QVulkanInstance` must be provided, since enumerating is not possible without it. Other fields in the backend-specific *params* will not actually be used by this function.

*nativeHandles* is optional. When specified, it must be a valid :sip:ref:`~PyQt6.QtGui.QRhiD3D11NativeHandles`, :sip:ref:`~PyQt6.QtGui.QRhiD3D12NativeHandles`, or :sip:ref:`~PyQt6.QtGui.QRhiVulkanNativeHandles`, similarly to :sip:ref:`~PyQt6.QtGui.QRhi.create`. However, unlike :sip:ref:`~PyQt6.QtGui.QRhi.create`, only the physical device (in case of Vulkan) or the adapter LUID (in case of D3D) fields are used, all other fields are ignored. This can be used the restrict the results to a given adapter. The returned list will contain 1 or 0 elements in this case.

Note how in the previous code snippet the looksGood() function implementation cannot perform any platform-specific filtering based on the true adapter / physical device identity, such as the adapter LUID on Windows or the VkPhysicalDevice with Vulkan. This is because :sip:ref:`~PyQt6.QtGui.QRhiDriverInfo` does not contain platform-specific data. Instead, use *nativeHandles* to get the results filtered already inside enumerateAdapters().

The following two snippets, using Direct 3D 12 as an example, are equivalent in practice:

::

    // enumerateAdapters-based approach from Qt 6.10 on
    QRhiD3D12InitParams initParams;
    QRhiD3D12NativeHandles nativeHandles;
    nativeHandles.adapterLuidLow = luid.LowPart; // retrieved a LUID from somewhere, now pass it on to Qt
    nativeHandles.adapterLuidHigh = luid.HighPart;
    QRhi::AdapterList adapters = QRhi::enumerateAdapters(QRhi::D3D12, &initParams, &nativeHandles);
    if (adapters.isEmpty()) { qWarning("Requested adapter was not found"); }
    QRhi *rhi = QRhi::create(QRhi::D3D12, &initParams, {}, nullptr, adapters[0]);
    qDeleteAll(adapters);

::

    // traditional approach, more lightweight
    QRhiD3D12InitParams initParams;
    QRhiD3D12NativeHandles nativeHandles;
    nativeHandles.adapterLuidLow = luid.LowPart; // retrieved a LUID from somewhere, now pass it on to Qt
    nativeHandles.adapterLuidHigh = luid.HighPart;
    QRhi *rhi = QRhi::create(QRhi::D3D12, &initParams, {}, &nativeHandles, nullptr);

.. seealso:: :sip:ref:`~PyQt6.QtGui.QRhi.create`.
