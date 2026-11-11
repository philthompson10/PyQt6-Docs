.. sip:method-description::
    :status: todo
    :pysig: a83331fd7a6dfed300489cb51f6cfa3f
    :realsig: (QRhiNativeHandles*)
    :digest: dbafbbf441c1ec2d235d0f07cfc751ee

With backends and graphics APIs where applicable, this function allows to provide additional arguments to the **next** submission of commands to the graphics command queue.

In particular, with Vulkan this allows passing in a list of Vulkan semaphore objects for ``vkQueueSubmit()`` to signal and wait on. *params* must then be a :sip:ref:`~PyQt6.QtGui.QRhiVulkanQueueSubmitParams`. This becomes essential in certain advanced use cases, such as when performing native Vulkan calls that involve having to wait on and signal VkSemaphores that the application's custom Vulkan rendering or compute code manages. In addition, this also allows specifying additional semaphores to wait on in the next ``vkQueuePresentKHR()``.

**Note:** This function affects the next queue submission only, which will happen in :sip:ref:`~PyQt6.QtGui.QRhi.endFrame`, :sip:ref:`~PyQt6.QtGui.QRhi.endOffscreenFrame`, or :sip:ref:`~PyQt6.QtGui.QRhi.finish`. The enqueuing of present happens in :sip:ref:`~PyQt6.QtGui.QRhi.endFrame`.

With many other backends the implementation of this function is a no-op.
