.. sip:method-description::
    :status: todo
    :pysig: 451483e275a33e2bd418317e0cd6070b
    :realsig: () const
    :digest: 359bfcfea3d4cb14ba17902af8232e8a

Gathers and returns statistics about the timings and allocations of graphics resources.

Data about memory allocations is only available with some backends, where such operations are under Qt's control. With graphics APIs where there is no lower level control over resource memory allocations, this will never be supported and all relevant fields in the results are 0.

With Vulkan in particular, the values are valid always, and are queried from the underlying memory allocator library. This gives an insight into the memory requirements of the active buffers and textures.

The same is true for Direct 3D 12. In addition to the memory allocator library's statistics, here the result also includes a ``totalUsageBytes`` field which reports the total size including additional resources that are not under the memory allocator library's control (swapchain buffers, descriptor heaps, etc.), as reported by DXGI.

The values correspond to all types of memory used, combined. (i.e. video + system in case of a discreet GPU)

Additional data, such as the total time in milliseconds spent in graphics and compute pipeline creation (which usually involves shader compilation or cache lookups, and potentially expensive processing) is available with most backends.

**Note:** The elapsed times for operations such as pipeline creation may be affected by various factors. The results should not be compared between different backends since the concept of "pipelines" and what exactly happens under the hood during, for instance, a call to QRhiGraphicsPipeline::create(), differ greatly between graphics APIs and their implementations.

**Note:** Additionally, many drivers will likely employ various caching strategies for shaders, programs, pipelines. (independently of Qt's own similar facilities, such as :sip:ref:`~PyQt6.QtGui.QRhi.setPipelineCacheData` or the OpenGL-specific program binary disk cache). Because such internal behavior is transparent to the API client, Qt and :sip:ref:`~PyQt6.QtGui.QRhi` have no knowledge or control over the exact caching strategy, persistency, invalidation of the cached data, etc. When reading timings, such as the time spent on pipeline creation, the potential presence and unspecified behavior of driver-level caching mechanisms should be kept in mind.
