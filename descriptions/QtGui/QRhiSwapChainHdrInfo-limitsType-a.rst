.. sip:attribute-description::
    :status: todo
    :digest: 52ee2d42fed03a43089f41b70e2e383d

With Metal on macOS/iOS, there is no luminance values exposed in the platform APIs. Instead, the maximum color component value, that would be 1.0 in a non-HDR setup, is provided. This value indicates what kind of information is available in limits.

.. seealso:: :sip:ref:`~PyQt6.QtGui.QRhiSwapChain.hdrInfo`.
