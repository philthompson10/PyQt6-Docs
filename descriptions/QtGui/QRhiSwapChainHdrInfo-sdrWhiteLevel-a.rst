.. sip:attribute-description::
    :status: todo
    :digest: 3e73957da9b4cd8e79131ea46589e9c7

On Windows this is the dynamic SDR white level in nits. The value is dependent on the screen brightness (on laptops), and the SDR or HDR Content Brightness settings in the Windows settings' System/Display/HDR view.

To perform white level correction for non-HDR (SDR) content, such as 2D UI elemenents, multiply the final color with sdrWhiteLevel / 80.0 whenever luminanceBehavior is :sip:ref:`~PyQt6.QtGui.QRhiSwapChainHdrInfo.LuminanceBehavior.SceneReferred`. (assuming Windows and a linear extended sRGB (scRGB) color space)

On other platforms the value is always a pre-defined value, 200. This may not match the system's actual SDR white level, but the value of this variable is not relevant in practice when the luminanceBehavior is :sip:ref:`~PyQt6.QtGui.QRhiSwapChainHdrInfo.LuminanceBehavior.DisplayReferred`, because then the color component value of 1.0 refers to the SDR white by default.

.. seealso:: luminanceBehavior.
