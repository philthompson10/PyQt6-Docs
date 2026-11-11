.. sip:class-description::
    :status: todo
    :brief: The base class for all QCanvasPainter gradient brushes
    :digest: 70abb619bbf398b0696f6f51df565b07

:sip:ref:`~PyQt6.QtCanvasPainter.QCanvasGradient` is the base class for all :sip:ref:`~PyQt6.QtCanvasPainter.QCanvasPainter` gradient brushes.

:sip:ref:`~PyQt6.QtCanvasPainter.QCanvasGradient` is the base class for all :sip:ref:`~PyQt6.QtCanvasPainter.QCanvasPainter` gradient brushes. Currently there are four type of gradients: :sip:ref:`~PyQt6.QtCanvasPainter.QCanvasLinearGradient`, :sip:ref:`~PyQt6.QtCanvasPainter.QCanvasRadialGradient`, :sip:ref:`~PyQt6.QtCanvasPainter.QCanvasConicalGradient` and :sip:ref:`~PyQt6.QtCanvasPainter.QCanvasBoxGradient`.

If no stops are provided with :sip:ref:`~PyQt6.QtCanvasPainter.QCanvasGradient.setStartColor`, :sip:ref:`~PyQt6.QtCanvasPainter.QCanvasGradient.setEndColor`, :sip:ref:`~PyQt6.QtCanvasPainter.QCanvasGradient.setColorAt` or :sip:ref:`~PyQt6.QtCanvasPainter.QCanvasGradient.setStops`, the gradient is rendered as transparent black (0,0,0,0). If only a single stop is provided, the gradient is filled with this color.

:sip:ref:`~PyQt6.QtCanvasPainter.QCanvasPainter` uses two different approaches for painting gradients.

* With maximum of 2 stops, the colors are passed into shader as 2 vec4 uniforms. This makes animating 2 stop gradients very performant, with no extra steps in between.

* With more than 2 stops, the colors are passed into shader as a one dimensional texture. By default the texture size is 1x256 pixels, optimized for quality and performance. The textures are cached, so when gradient stops or colors don't change, previous texture can be reused even when other gradient properties (like position, angle etc.) change. Although animating multi-stop gradients is fast, it will cause texture uploads, so consider if it is worth it.

There are few environment variables to control the gradients texture usage:

* QCPAINTER_DISABLE_TEXTURE_USAGE_TRACKING - By default, gradient texture usage is tracked and kept under the max amount. Set this environment variable to disable the tracking and keep all gradient textures in memory.

* QCPAINTER_MAX_TEXTURES - By default, the maximum amount of textures is ``1024``. Set this environt variable to contain number of desired maximum texture amount. The currently unused temporary gradient textures are automatically removed when the maximum amount is reached.

  **Note:** This does not have an effect when the texture usage tracking has been disabled.
