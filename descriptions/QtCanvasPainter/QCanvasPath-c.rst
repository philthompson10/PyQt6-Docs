.. sip:class-description::
    :status: todo
    :brief: The native path format of QCanvasPainter
    :digest: 8adccefb661ce72b401b0d259c57874b

:sip:ref:`~PyQt6.QtCanvasPainter.QCanvasPath` is the native path format of :sip:ref:`~PyQt6.QtCanvasPainter.QCanvasPainter`.

A painter path is an object composed of a number of graphical building blocks, such as rectangles, ellipses, lines, and curves. :sip:ref:`~PyQt6.QtCanvasPainter.QCanvasPath` API matches to :sip:ref:`~PyQt6.QtCanvasPainter.QCanvasPainter` path painting, making it easy to adjust code between painting directly or painting into a path. The main reason use :sip:ref:`~PyQt6.QtCanvasPainter.QCanvasPath` is to avoid recreating paths that are static and used in every frame of the rendering, and to possibly enable the caching of the path-related rendering data (such, as the vertex and index data generated from it), instead of regenerating it every time the path is filled or stroked.

Compared to :sip:ref:`~PyQt6.QtGui.QPainterPath`, :sip:ref:`~PyQt6.QtCanvasPainter.QCanvasPath` is more optimized for rendering with fewer features for comparing or adjusting the paths. In particular:

* There are no methods for intersection or subtraction between two paths.

* There is no method for translating the path.

* There is no method for adding text.

From a functionality point of view, :sip:ref:`~PyQt6.QtCanvasPainter.QCanvasPath` is more similar to HTML Canvas `Path2D <https://developer.mozilla.org/en-US/docs/Web/API/Path2D>`_, with some additions and the API matching to :sip:ref:`~PyQt6.QtCanvasPainter.QCanvasPainter`.

.. _qcanvaspath-path-groups-and-caching:

Path Groups and Caching
-----------------------

Painting paths through :sip:ref:`~PyQt6.QtCanvasPainter.QCanvasPath` allows the engine to cache the path geometry (vertices). This improves the performance of static paths, while potentially increasing CPU and GPU memory consumption.

When painting paths using :sip:ref:`~PyQt6.QtCanvasPainter.QCanvasPainter.fill` or :sip:ref:`~PyQt6.QtCanvasPainter.QCanvasPainter.stroke` that take :sip:ref:`~PyQt6.QtCanvasPainter.QCanvasPath` as a parameter, it is possible to set a ``pathGroup`` as a second parameter.

By default, ``pathGroup`` is ``-1``, which means that the path data will not be attempted to be cached, and so rendering happens mostly identically to when doing direct painting using beginPath(), followed by path definition commands, and finally a fill or stroke.

Setting ``pathGroup`` to a value of ``0`` or any higher number will enable the caching and reuse of the path's generated geometry. Arranging paths into path groups allows efficient optimization of the rendering performance and memory usage. Paths that belong together and often change at the same time should be in the same group for optimal results.

When the path changes, its data, even if it was cached, is automatically updated. Things that cause a geometry update of the path group are:

* Clearing the path elements or adding new elements.

* Changing the stroke line width (\ :sip:ref:`~PyQt6.QtCanvasPainter.QCanvasPainter.setLineWidth`, relevant for strokes).

* Adjusting antialiasing amount (\ :sip:ref:`~PyQt6.QtCanvasPainter.QCanvasPainter.setAntialias`, relevant both for fills and strokes).

* Changing line cap or line join type (\ :sip:ref:`~PyQt6.QtCanvasPainter.QCanvasPainter.setLineCap`, :sip:ref:`~PyQt6.QtCanvasPainter.QCanvasPainter.setLineJoin`, relevant for strokes).

* Changing :sip:ref:`~PyQt6.QtCanvasPainter.QCanvasPainter.setWindingEnforce` (relevant both for fills and strokes).

* Changing :sip:ref:`~PyQt6.QtCanvasPainter.QCanvasPainter.setHighQualityStroking` (relevant both for fills and strokes).

Note that changing the state transform (\ :sip:ref:`~PyQt6.QtCanvasPainter.QCanvasPainter.transform`, :sip:ref:`~PyQt6.QtCanvasPainter.QCanvasPainter.rotate` etc.) does not invalidate the path, so moving/scaling/rotating a cached path is very efficient.

As an example, consider a :sip:ref:`~PyQt6.QtCanvasPainter.QCanvasPath` ``p`` with a very large number of commands in it. Stroking or filling this path ``p`` can be an expensive operation due to the amount of work performed on the CPU side. The vertex data may be regenerated and uploaded into GPU buffers for each of those stroke or fill operation, in every frame. That is not ideal when the path is static and all we want is to draw it again and again in every frame as efficiently as possible.

When a path group is specifed, for example replacing ``stroke(p)`` with ``stroke(p, 5)``, then the renderer has the option to maintain dedicated vertex and index buffers for path ``p``, and any other path that has the same group (``5``) specified in a stroke or fill command.

Assuming that path ``p`` (the commands in the :sip:ref:`~PyQt6.QtCanvasPainter.QCanvasPath`) do not change, repeatedly filling or stroking this path will become a cheap operation, because all data is already there in the GPU buffers dedicated to path group ``5``. Transforming is also cheap, since with cached path groups transformations happen in the vertex shader, not on the geometry itself.

In the following code snippet, when ``m_path`` is complex enough, its commands do not change, and it is stroked with the same stroke width, antialiasing amount, etc. in every frame, then the following can be significantly more efficient than not using path groups:

::

    // m_path is QCanvasPath with lots of commands in it
    const int pathGroup = 5;

    // in every frame:
      painter->stroke(m_path, pathGroup);
      // ... other draw commands
      painter->translate(100, 0);
      painter->stroke(m_path, pathGroup);
      // ... other draw commands

When stroking ``m_path`` the second, third, and later times, the rendering will be very cheap compared to not using path groups, because no path geometry processing will need to happen on the CPU side. Changing the transform by applying a translation does not invalidate the cached path group data, hence the translated stroke() call is just as fast.

What happens if one of the relevant states listed above change? For example, if the path is drawn with two different stroke widths:

::

    // m_path is QCanvasPath with lots of commands in it
    const int pathGroup = 5;

    // in every frame:
      painter->setStrokeWidth(4);
      painter->stroke(m_path, pathGroup);
      // ... other draw commands
      painter->translate(100, 0);
      painter->setStrokeWidth(8);
      painter->stroke(m_path, pathGroup);
      // ... other draw commands

This is still very efficient, since the path vertex data will be cached and reused for both stroke width 4 and 8, but the resource usage will increase slightly, since the GPU buffer for path group ``5`` will now contain both the stroke width 4 and 8 version of the path geometry.

One way to think of path groups is a caching mechanism where the path group value is treated as the first level cache key, while the :sip:ref:`~PyQt6.QtCanvasPainter.QCanvasPath` object, the antialiasing amount, the render hints, and, in case of stroking, the stroke width, line cap, and line join form the second level cache key (within the path group).

Changing the path commands (the elements in the :sip:ref:`~PyQt6.QtCanvasPainter.QCanvasPath`) is always expensive, because that will always lead to rebuilding the associated data on the CPU and GPU side. As a somewhat extreme example, if a :sip:ref:`~PyQt6.QtCanvasPainter.QCanvasPath` changes its commands in every frame, then there is no point in using path groups (and :sip:ref:`~PyQt6.QtCanvasPainter.QCanvasPath`, even) for that particular path, as there are no benefits compared to direct path drawing via :sip:ref:`~PyQt6.QtCanvasPainter.QCanvasPainter` functions.

In cases where the path group will not be used anymore in drawing, or the application wants to free up memory as much as possible, the cache can be released by calling :sip:ref:`~PyQt6.QtCanvasPainter.QCanvasPainter.removePathGroup`. This isn't usually needed, as the cached paths are automatically released during the painter destructor.

.. seealso:: :sip:ref:`~PyQt6.QtCanvasPainter.QCanvasPainter.addPath`, :sip:ref:`~PyQt6.QtCanvasPainter.QCanvasPainter.removePathGroup`.
