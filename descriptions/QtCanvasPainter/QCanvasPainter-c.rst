.. sip:class-description::
    :status: todo
    :brief: Performs hardware-accelerated painting on QRhi
    :digest: 57474c26934b2f3d5c291c90edf521e1

The :sip:ref:`~PyQt6.QtCanvasPainter.QCanvasPainter` class performs hardware-accelerated painting on :sip:ref:`~PyQt6.QtGui.QRhi`.

Qt Canvas Painter (\ :sip:ref:`~PyQt6.QtCanvasPainter.QCanvasPainter`) provides painting API optimized for hardware-accelerated (GPU) painting. The API closely follows the HTML Canvas 2D Context specification, ported to Qt C++. It is also influenced by :sip:ref:`~PyQt6.QtGui.QPainter`, but with a more compact API.

Here is a simple example of using :sip:ref:`~PyQt6.QtCanvasPainter.QCanvasPainter` to create a round button.

+--------------------------------------+---------------------------------------------------------------+
| |image-qcpainter-buttonexample-webp| | ::                                                            |
|                                      |                                                               |
|                                      |     QRectF rect(40, 70, 120, 60);                             |
|                                      |     QRectF shadowRect = rect.translated(2, 4);                |
|                                      |     // Paint shadow                                           |
|                                      |     QCanvasBoxShadow shadow(shadowRect);                      |
|                                      |     shadow.setRadius(30);                                     |
|                                      |     shadow.setBlur(15);                                       |
|                                      |     shadow.setColor("#60373F26");                             |
|                                      |     p->drawBoxShadow(shadow);                                 |
|                                      |     // Paint rounded rect                                     |
|                                      |     p->beginPath();                                           |
|                                      |     p->roundRect(rect, 30);                                   |
|                                      |     p->setFillStyle("#DBEB00");                               |
|                                      |     p->fill();                                                |
|                                      |     // Paint text                                             |
|                                      |     p->setTextAlign(QCanvasPainter::TextAlign::Center);       |
|                                      |     p->setTextBaseline(QCanvasPainter::TextBaseline::Middle); |
|                                      |     QFont font("Titillium Web", 18);                          |
|                                      |     p->setFont(font);                                         |
|                                      |     p->setFillStyle("#373F26");                               |
|                                      |     p->fillText("CLICK!", rect);                              |
+--------------------------------------+---------------------------------------------------------------+

Here is another example of painting a simple graph.

+-------------------------------------+-----------------------------------------------------+
| |image-qcpainter-graphexample-webp| | ::                                                  |
|                                     |                                                     |
|                                     |     // Paint grid                                   |
|                                     |     QCanvasGridPattern grid(0, 0, 10, 10);          |
|                                     |     grid.setLineColor("#404040");                   |
|                                     |     grid.setBackgroundColor("#202020");             |
|                                     |     p->setFillStyle(grid);                          |
|                                     |     p->fillRect(0, 0, width(), height());           |
|                                     |     // Paint axis                                   |
|                                     |     p->setFillStyle(QColorConstants::White);        |
|                                     |     p->fillRect(0, 0.5 * height() - 1, width(), 2); |
|                                     |     p->fillRect(0.5 * width() - 1, 0, 2, height()); |
|                                     |     // Paint shadowed graph                         |
|                                     |     p->beginPath();                                 |
|                                     |     p->moveTo(20, height() * 0.8);                  |
|                                     |     p->bezierCurveTo(width() * 0.2, height() * 0.4, |
|                                     |                      width() * 0.5, height() * 0.8, |
|                                     |                      width() - 20, height() * 0.2); |
|                                     |     p->setAntialias(10);                            |
|                                     |     p->setLineWidth(12);                            |
|                                     |     p->setStrokeStyle("#D0000000");                 |
|                                     |     p->stroke();                                    |
|                                     |     p->setAntialias(1);                             |
|                                     |     p->setLineWidth(6);                             |
|                                     |     QCanvasLinearGradient lg(0, 0, 0, height());    |
|                                     |     lg.setStartColor(QColorConstants::Red);         |
|                                     |     lg.setEndColor(QColorConstants::Green);         |
|                                     |     p->setStrokeStyle(lg);                          |
|                                     |     p->stroke();                                    |
+-------------------------------------+-----------------------------------------------------+

.. _qcanvaspainter-features:

Features
--------

For the most part, and from the naming perspective, :sip:ref:`~PyQt6.QtCanvasPainter.QCanvasPainter` follows HTML Canvas 2D Context (https://html.spec.whatwg.org/multipage/canvas.html#2dcontext). This makes the API familiar to use for many developers, and with the ability to easily reuse existing canvas code. But the aim is NOT to be 100% compatible with the HTML canvas. :sip:ref:`~PyQt6.QtCanvasPainter.QCanvasPainter` omits some of the features to make it simpler, more performant on :sip:ref:`~PyQt6.QtGui.QRhi` hardware accelerated graphics API, and to better target modern UI needs. Due to these reasons, :sip:ref:`~PyQt6.QtCanvasPainter.QCanvasPainter` also has additional features compared to HTML Canvas 2D Context.

These are some of the functionality that are at least currently missing compared to HTML Canvas:

* Clipping: All clipping is (transformed) rectangle and clipping to path shapes is not supported.

* Dashes: Strokes are always solid lines, dashed/dotted stroke patterns are not supported.

* Path testing: There are no isPointInPath() or isPointInStroke() methods.

* Text stroking: No support for outline stroking of text.

* Filter: Canvas SVG filter effects are not supported.

* CompositeModes: The number of composite modes is limited to 3, which can be supported without rendering into extra buffers.

* Shadows: Built-in shadow methods are not supported.

On the other hand, some of the additional features :sip:ref:`~PyQt6.QtCanvasPainter.QCanvasPainter` offers compared to HTML Canvas include:

* Path groups: :sip:ref:`~PyQt6.QtCanvasPainter.QCanvasPainter` allows painting to static paths and caching these paths as groups for optimal GPU usage.

* Adjustable antialiasing: Due to path vertex antialiasing and SDF text rendering, the pixel amount of antialiasing can be freely adjusted for smoother painting.

* Box Gradient: In addition to linear, radial and conical gradients, :sip:ref:`~PyQt6.QtCanvasPainter.QCanvasPainter` also supports rounded rectangle box gradient.

* Box Shadow: :sip:ref:`~PyQt6.QtCanvasPainter.QCanvasPainter` also supports CSS box-shadow type of brush. The rendering uses a SDF approach similar to Qt Quick `RectangularShadow <https://doc.qt.io/qt-6/qml-qtquick-effects-rectangularshadow.html>`_, making it very performant.

* Grid patterns: :sip:ref:`~PyQt6.QtCanvasPainter.QCanvasPainter` supports :sip:ref:`~PyQt6.QtCanvasPainter.QCanvasGridPattern` for dynamic grid and bar pattern styles.

* Custom brushes: :sip:ref:`~PyQt6.QtCanvasPainter.QCanvasPainter` also allows filling & stroking with custom vertex and fragment shaders (\ :sip:ref:`~PyQt6.QtCanvasPainter.QCanvasCustomBrush`). These custom brushes can also be used for text.

* Text wrapping: :sip:ref:`~PyQt6.QtCanvasPainter.QCanvasPainter` supports automatic wrapping of text into multiple lines, with different wrapping modes.

* Color effects: In addition to globalAlpha, :sip:ref:`~PyQt6.QtCanvasPainter.QCanvasPainter` also supports global brightness, contrast and saturation.

* Tinted images: :sip:ref:`~PyQt6.QtCanvasPainter.QCanvasPainter` adds tint color support for painted images and image patterns.

:sip:ref:`~PyQt6.QtCanvasPainter.QCanvasPainter` is architecture agnostic, and usable for both Qt Quick and Qt Widgets applications. Actually, it is usable even without either of those, with just :sip:ref:`~PyQt6.QtGui.QWindow` and :sip:ref:`~PyQt6.QtGui.QRhi`. To utilize :sip:ref:`~PyQt6.QtCanvasPainter.QCanvasPainter`, use it from one of these classes, depending on the architecture of your application:

* Qt Quick: Use :sip:ref:`~PyQt6.QtCanvasPainter.QCanvasPainterItem` and :sip:ref:`~PyQt6.QtCanvasPainter.QCanvasPainterItemRenderer`.

* Qt Widgets: Use :sip:ref:`~PyQt6.QtCanvasPainter.QCanvasPainterWidget`.

* :sip:ref:`~PyQt6.QtGui.QRhi`-based :sip:ref:`~PyQt6.QtGui.QWindow`, or offscreen :sip:ref:`~PyQt6.QtGui.QRhi` buffers: Use QCanvasPainterFactory and QCanvasRhiPaintDriver.

.. _qcanvaspainter-winding-rules:

Winding rules
-------------

:sip:ref:`~PyQt6.QtCanvasPainter.QCanvasPainter` uses :sip:ref:`~PyQt6.QtCanvasPainter.QCanvasPainter.FillRule.NonZero` ({\ :sip:ref:`~PyQt6.QtCore.Qt.FillRule.WindingFill`}) fillrule by default. To select the filling based on the path points direction, disable the winding forcing by calling :sip:ref:`~PyQt6.QtCanvasPainter.QCanvasPainter.setWindingEnforce`.

+-------------------------------------+--------------------------------------+
| |image-qcpainter-pathwinding2-webp| | ::                                   |
|                                     |                                      |
|                                     |     p->setWindingEnforce(false);     |
|                                     |     p->beginPath();                  |
|                                     |     // Outer shape, counterclockwise |
|                                     |     p->moveTo(20, 20);               |
|                                     |     p->lineTo(100, 180);             |
|                                     |     p->lineTo(180, 20);              |
|                                     |     p->closePath();                  |
|                                     |     // Inner shape, clockwise        |
|                                     |     p->moveTo(100, 40);              |
|                                     |     p->lineTo(125, 90);              |
|                                     |     p->lineTo(75, 90);               |
|                                     |     p->closePath();                  |
|                                     |     p->fill();                       |
|                                     |     p->stroke();                     |
+-------------------------------------+--------------------------------------+

However, a more common case is relying on winding enforcing and setting the preferred winding using :sip:ref:`~PyQt6.QtCanvasPainter.QCanvasPainter.setPathWinding` or :sip:ref:`~PyQt6.QtCanvasPainter.QCanvasPainter.beginHoleSubPath` and :sip:ref:`~PyQt6.QtCanvasPainter.QCanvasPainter.beginSolidSubPath` helpers.

+-------------------------------------+-----------------------------------------+
| |image-qcpainter-pathwinding3-webp| | ::                                      |
|                                     |                                         |
|                                     |     p->beginPath();                     |
|                                     |     p->roundRect(20, 20, 160, 160, 30); |
|                                     |     // Start painting holes             |
|                                     |     p->beginHoleSubPath();              |
|                                     |     p->roundRect(40, 40, 120, 120, 10); |
|                                     |     // Start painting solid             |
|                                     |     p->beginSolidSubPath();             |
|                                     |     p->rect(60, 60, 80, 20);            |
|                                     |     p->circle(100, 120, 20);            |
|                                     |     p->fill();                          |
|                                     |     p->stroke();                        |
+-------------------------------------+-----------------------------------------+

.. |image-qcpainter-buttonexample-webp| image:: ../../../images/qcpainter-buttonexample.webp
.. |image-qcpainter-graphexample-webp| image:: ../../../images/qcpainter-graphexample.webp
.. |image-qcpainter-pathwinding2-webp| image:: ../../../images/qcpainter-pathwinding2.webp
.. |image-qcpainter-pathwinding3-webp| image:: ../../../images/qcpainter-pathwinding3.webp
