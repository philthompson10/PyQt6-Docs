.. sip:enum-description::
    :status: todo
    :digest: 6cf6929869244a69c939e11b3e8012a5

Describes the swapchain format. The default format is SDR.

This enum is used with isFormatSupported() to check upfront if creating the swapchain with the given format is supported by the platform and the window's associated screen, and with setFormat() to set the requested format in the swapchain before calling createOrResize() for the first time.
