.. sip:method-description::
    :status: todo
    :pysig: a5704e7d57089c440a7d83c72d987b9e
    :realsig: ()
    :digest: 66d919d50e12990a2876e71ef075cbb5

Returns a binary data blob with data collected from the :sip:ref:`~PyQt6.QtGui.QRhiGraphicsPipeline` and :sip:ref:`~PyQt6.QtGui.QRhiComputePipeline` successfully created during the lifetime of this :sip:ref:`~PyQt6.QtGui.QRhi`.

By saving and then, in subsequent runs of the same application, reloading the cache data, pipeline and shader creation times can potentially be reduced. What exactly the cache and its serialized version includes is not specified, is always specific to the backend used, and in some cases also dependent on the particular implementation of the graphics API.

When the :sip:ref:`~PyQt6.QtGui.QRhi.Feature.PipelineCacheDataLoadSave` is reported as unsupported, the returned :sip:ref:`~PyQt6.QtCore.QByteArray` is empty.

When the :sip:ref:`~PyQt6.QtGui.QRhi.Flag.EnablePipelineCacheDataSave` flag was not specified when calling :sip:ref:`~PyQt6.QtGui.QRhi.create`, the returned :sip:ref:`~PyQt6.QtCore.QByteArray` may be empty, even when the :sip:ref:`~PyQt6.QtGui.QRhi.Feature.PipelineCacheDataLoadSave` feature is supported.

When the returned data is non-empty, it is always specific to the Qt version and :sip:ref:`~PyQt6.QtGui.QRhi` backend. In addition, in some cases there is a strong dependency to the graphics device and the exact driver version used. :sip:ref:`~PyQt6.QtGui.QRhi` takes care of adding the appropriate header and safeguards that ensure that the data can always be passed safely to :sip:ref:`~PyQt6.QtGui.QRhi.setPipelineCacheData`, therefore attempting to load data from a run on another version of a driver will be handled safely and gracefully.

**Note:** Calling :sip:ref:`~PyQt6.QtGui.QRhi.releaseCachedResources` may, depending on the backend, clear the pipeline data collected. A subsequent call to this function may then not return any data.

See :sip:ref:`~PyQt6.QtGui.QRhi.Flag.EnablePipelineCacheDataSave` for further details about this feature.

**Note:** Minimize the number of calls to this function. Retrieving the blob is not always a cheap operation, and therefore this function should only be called at a low frequency, ideally only once e.g. when closing the application.

.. seealso:: :sip:ref:`~PyQt6.QtGui.QRhi.setPipelineCacheData`, :sip:ref:`~PyQt6.QtGui.QRhi.create`, :sip:ref:`~PyQt6.QtGui.QRhi.isFeatureSupported`.
