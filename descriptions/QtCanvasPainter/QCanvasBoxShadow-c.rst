.. sip:class-description::
    :status: todo
    :brief: Brush for painting rectangle shadows / glows
    :digest: 7e59e34108864f54f4dda90c0ba8592a

:sip:ref:`~PyQt6.QtCanvasPainter.QCanvasBoxShadow` is a brush for painting rectangle shadows / glows.

:sip:ref:`~PyQt6.QtCanvasPainter.QCanvasBoxShadow` is a rounded rectangle brush with blur applied. The performance of :sip:ref:`~PyQt6.QtCanvasPainter.QCanvasBoxShadow` is much better than a general shadow that creates blurred shadow/glow of any shaped item, as it uses SDF approach.

The features of :sip:ref:`~PyQt6.QtCanvasPainter.QCanvasBoxShadow` are similar to CSS box-shadow, with radius, spread, blur and color values. The rendering output also matches the CSS box-shadow, with few notable differences to make the :sip:ref:`~PyQt6.QtCanvasPainter.QCanvasBoxShadow` as high-performance as possible. Blurring is calculated mathematically in the shader rather than using Gaussian blur, which CSS box-shadow implementations often use. This makes the shadow look slightly different, especially when the blur amount grows bigger than half of the shadow width / height.

Here are screenshots to compare the rendering output of :sip:ref:`~PyQt6.QtCanvasPainter.QCanvasBoxShadow` and CSS box-shadow in the Chrome browser. These show how blur radius of 0, 10, 20 and 40 pixels affect smaller shadows.

CSS box-shadow:

.. image:: ../../../images/examples_css_box_shadow.png

:sip:ref:`~PyQt6.QtCanvasPainter.QCanvasBoxShadow`:

.. image:: ../../../images/examples_qcpainter_box_shadow.png
