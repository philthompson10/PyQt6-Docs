.. sip:method-description::
    :status: todo
    :pysig: c70916e782d9742b90f37ccdedc4f900
    :realsig: (const QByteArray&)
    :digest: 9236aa200c8e6d95ae5b1f684057ecae

Loads *data* into the pipeline cache, when applicable.

When the :sip:ref:`~PyQt6.QtGui.QRhi.Feature.PipelineCacheDataLoadSave` is reported as unsupported, the function is safe to call, but has no effect.

The blob returned by :sip:ref:`~PyQt6.QtGui.QRhi.pipelineCacheData` is always specific to the Qt version, the :sip:ref:`~PyQt6.QtGui.QRhi` backend, and, in some cases, also to the graphics device, and a given version of the graphics driver. :sip:ref:`~PyQt6.QtGui.QRhi` takes care of adding the appropriate header and safeguards that ensure that the data can always be passed safely to this function. If there is a mismatch, e.g. because the driver has been upgraded to a newer version, or because the data was generated from a different :sip:ref:`~PyQt6.QtGui.QRhi` backend, a warning is printed and *data* is safely ignored.

With Vulkan, this maps directly to VkPipelineCache. Calling this function creates a new Vulkan pipeline cache object, with its initial data sourced from *data*. The pipeline cache object is then used by all subsequently created :sip:ref:`~PyQt6.QtGui.QRhiGraphicsPipeline` and :sip:ref:`~PyQt6.QtGui.QRhiComputePipeline` objects, thus accelerating, potentially, the pipeline creation.

With other APIs there is no real pipeline cache, but they may provide a cache with bytecode from shader compilations (D3D) or program binaries (OpenGL). In applications that perform a lot of shader compilation from source at run time this can provide a significant boost in subsequent runs if the "pipeline cache" is pre-seeded from an earlier run using this function.

**Note:** :sip:ref:`~PyQt6.QtGui.QRhi` cannot give any guarantees that *data* has an effect on the pipeline and shader creation performance. With APIs like Vulkan, it is up to the driver to decide if *data* is used for some purpose, or if it is ignored.

See :sip:ref:`~PyQt6.QtGui.QRhi.Flag.EnablePipelineCacheDataSave` for further details about this feature.

**Note:** This mechanism offered by :sip:ref:`~PyQt6.QtGui.QRhi` is independent of the drivers' own internal caching mechanism, if any. This means that, depending on the graphics API and its implementation, the exact effects of retrieving and then reloading *data* are not predictable. Improved performance may not be visible at all in case other caching mechanisms outside of Qt's control are already active.

**Note:** Minimize the number of calls to this function. Loading the blob is not always a cheap operation, and therefore this function should only be called at a low frequency, ideally only once e.g. when starting the application.

**Warning:** Serialized pipeline cache data is assumed to be trusted content. Qt performs robust parsing of the header and metadata included in *data*, application developers are however advised to never pass in data from untrusted sources.

.. seealso:: :sip:ref:`~PyQt6.QtGui.QRhi.pipelineCacheData`, :sip:ref:`~PyQt6.QtGui.QRhi.isFeatureSupported`.
