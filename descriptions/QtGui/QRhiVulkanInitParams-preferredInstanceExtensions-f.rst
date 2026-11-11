.. sip:method-description::
    :status: todo
    :pysig: 95bc3d14303f22e358f6ff12558385a3
    :realsig: ()
    :digest: 0ff83717cf4fd4fd4393124103038e01

Returns the list of instance extensions that are expected to be enabled on the :sip:ref:`~PyQt6.QtGui.QVulkanInstance` that is used for the Vulkan-based :sip:ref:`~PyQt6.QtGui.QRhi`.

The returned list can be safely passed to QVulkanInstance::setExtensions() as-is, because unsupported extensions are filtered out automatically.
