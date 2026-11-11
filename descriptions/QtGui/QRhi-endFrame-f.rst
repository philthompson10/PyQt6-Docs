.. sip:method-description::
    :status: todo
    :pysig: 559f43f03b5e006b91a0de083bcc67f3
    :realsig: (QRhiSwapChain*, QRhi::EndFrameFlags)
    :digest: c69ab59af9f5ca4d7951dc7b7636209e

Ends, commits, and presents a frame that was started in the last :sip:ref:`~PyQt6.QtGui.QRhi.beginFrame` on *swapChain*.

Double (or triple) buffering is managed internally by the :sip:ref:`~PyQt6.QtGui.QRhiSwapChain` and :sip:ref:`~PyQt6.QtGui.QRhi`.

*flags* can optionally be used to change the behavior in certain ways. Passing :sip:ref:`~PyQt6.QtGui.QRhi.EndFrameFlag.SkipPresent` skips queuing the Present command or calling swapBuffers.

Returns :sip:ref:`~PyQt6.QtGui.QRhi.FrameOpResult.FrameOpSuccess` on success, or another :sip:ref:`~PyQt6.QtGui.QRhi.FrameOpResult` value on failure. Some of these should be treated as soft, "try again later" type of errors: When :sip:ref:`~PyQt6.QtGui.QRhi.FrameOpResult.FrameOpSwapChainOutOfDate` is returned, the swapchain is to be resized or updated by calling QRhiSwapChain::createOrResize(). The application should then attempt to generate a new frame. :sip:ref:`~PyQt6.QtGui.QRhi.FrameOpResult.FrameOpDeviceLost` means the graphics device is lost but this may also be recoverable by releasing all resources, including the :sip:ref:`~PyQt6.QtGui.QRhi` itself, and then recreating all resources. See :sip:ref:`~PyQt6.QtGui.QRhi.isDeviceLost` for further discussion.

.. seealso:: :sip:ref:`~PyQt6.QtGui.QRhi.beginFrame`, :sip:ref:`~PyQt6.QtGui.QRhi.isDeviceLost`.
