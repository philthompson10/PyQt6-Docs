.. sip:method-description::
    :status: todo
    :pysig: fa7153f7ed1cb6c0fcf2ffb2fac21748
    :realsig: (int)
    :digest: e99a9e3e530bbc8979188b0eec8107d0

With some graphics APIs, such as Vulkan, integrating custom rendering code that uses the graphics API directly needs special care when it comes to image layouts. This function allows communicating the expected *layout* the image backing the :sip:ref:`~PyQt6.QtGui.QRhiTexture` is in after the native rendering commands.

For example, consider rendering into a :sip:ref:`~PyQt6.QtGui.QRhiTexture`'s VkImage directly with Vulkan in a code block enclosed by :sip:ref:`~PyQt6.QtGui.QRhiCommandBuffer.beginExternal` and :sip:ref:`~PyQt6.QtGui.QRhiCommandBuffer.endExternal`, followed by using the image for texture sampling in a :sip:ref:`~PyQt6.QtGui.QRhi`-based render pass. To avoid potentially incorrect image layout transitions, this function can be used to indicate what the image layout will be once the commands recorded in said code block complete.

Calling this function makes sense only after :sip:ref:`~PyQt6.QtGui.QRhiCommandBuffer.endExternal` and before a subsequent :sip:ref:`~PyQt6.QtGui.QRhiCommandBuffer.beginPass`.

This function has no effect with :sip:ref:`~PyQt6.QtGui.QRhi` backends where the underlying graphics API does not expose a concept of image layouts.

**Note:** With Vulkan *layout* is a ``VkImageLayout``. With Direct 3D 12 *layout* is a value composed of the bits from ``D3D12_RESOURCE_STATES``.
