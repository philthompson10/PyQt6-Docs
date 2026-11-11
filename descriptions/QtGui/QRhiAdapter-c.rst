.. sip:class-description::
    :status: todo
    :brief: Represents a physical graphics device
    :digest: ddf2d55e4c7667543414a3fb285f70ba

Represents a physical graphics device.

Some :sip:ref:`~PyQt6.QtGui.QRhi` backends target graphics APIs that expose the concept of ``adapters`` or ``physical devices``. Call the static :sip:ref:`~PyQt6.QtGui.QRhi.enumerateAdapters` function to retrieve a list of the adapters present in the system. Pass one of the returned :sip:ref:`~PyQt6.QtGui.QRhiAdapter` objects to :sip:ref:`~PyQt6.QtGui.QRhi.create` in order to request using the adapter or physical device the :sip:ref:`~PyQt6.QtGui.QRhiAdapter` corresponds to. Other than exposing the :sip:ref:`~PyQt6.QtGui.QRhiDriverInfo`, :sip:ref:`~PyQt6.QtGui.QRhiAdapter` is to be treated as an opaque handle.

**Note:** With Vulkan, the :sip:ref:`~PyQt6.QtGui.QRhiAdapter` is valid only as long as the :sip:ref:`~PyQt6.QtGui.QVulkanInstance` that was used for :sip:ref:`~PyQt6.QtGui.QRhi.enumerateAdapters` is valid. This also means that a :sip:ref:`~PyQt6.QtGui.QRhiAdapter` is tied to the Vulkan instance (\ :sip:ref:`~PyQt6.QtGui.QVulkanInstance`, ``VkInstance``) and cannot be used in the context of another Vulkan instance.

**Note:** This is a RHI API with limited compatibility guarantees, see :sip:ref:`~PyQt6.QtGui.QRhi` for details.
