.. sip:method-description::
    :status: todo
    :pysig: 63a860829309b2bcfe34dffa66b8c2b7
    :realsig: ()
    :digest: 9c703030b79f21941d719b66b5a9cdfa

Returns the HDR information for the associated display.

Do not assume that this is a cheap operation. Depending on the platform, this function makes various platform queries which may have a performance impact.

**Note:** Can be called before createOrResize() as long as the window is set.

**Note:** What happens when moving a window with an initialized swapchain between displays (HDR to HDR with different characteristics, HDR to SDR, etc.) is not currently well-defined and depends heavily on the windowing system and compositor, with potentially varying behavior between platforms. Currently :sip:ref:`~PyQt6.QtGui.QRhi` only guarantees that hdrInfo() returns valid data, if available, for the display to which the swapchain's associated window belonged at the time of createOrResize().

.. seealso:: :sip:ref:`~PyQt6.QtGui.QRhiSwapChainHdrInfo`.
