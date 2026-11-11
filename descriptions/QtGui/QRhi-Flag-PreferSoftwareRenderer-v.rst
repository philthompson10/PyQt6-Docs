.. sip:enum-member-description::
    :status: todo
    :value: 1 << 1
    :digest: eef0e673e9ff422048cfe59fa735a362

Indicates that backends should prefer choosing an adapter or physical device that renders in software on the CPU. For example, with Direct3D there is typically a "Basic Render Driver" adapter available with ``DXGI_ADAPTER_FLAG_SOFTWARE``. Setting this flag requests the backend to choose that adapter over any other, as long as no specific adapter was forced by other backend-specific means. With Vulkan this maps to preferring physical devices with ``VK_PHYSICAL_DEVICE_TYPE_CPU``. When not available, or when it is not possible to decide if an adapter/device is software-based, this flag is ignored. It may also be ignored with graphics APIs that have no concept and means of enumerating adapters/devices.
