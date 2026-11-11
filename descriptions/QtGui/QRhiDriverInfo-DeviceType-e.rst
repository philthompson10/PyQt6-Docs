.. sip:enum-description::
    :status: todo
    :digest: 420a10e4e4706880ca33ff89b7100a43

Specifies the graphics device's type, when the information is available.

In practice this is only applicable with Vulkan and Metal. With Direct 3D 11 and 12, using an adapter with the software flag set leads to the value ``CpuDevice``. Otherwise, and with OpenGL, the value is always UnknownDevice.
