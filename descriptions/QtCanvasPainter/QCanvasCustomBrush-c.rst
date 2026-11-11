.. sip:class-description::
    :status: todo
    :brief: Brush with custom shaders
    :digest: eb977b87d75dc96b3db41313a6dc60c6

:sip:ref:`~PyQt6.QtCanvasPainter.QCanvasCustomBrush` is a brush with custom shaders.

:sip:ref:`~PyQt6.QtCanvasPainter.QCanvasCustomBrush` is a stroke/fill brush with custom vertex and/or fragment shaders.

These shaders are expected to be written in Vulkan-style GLSL, similarly to Qt Quick `ShaderEffect <https://doc.qt.io/qt-6/qml-qtquick-shadereffect.html>`_ shaders. They must always contain a ``QC_INCLUDE`` statement, either with ``"customfrag.glsl"`` or ``"customvert.glsl"``. This makes available a uniform block, the image and font textures, and a few helper functions.

``iTime`` is an example of a commonly used member in the built-in uniform block. Calling :sip:ref:`~PyQt6.QtCanvasPainter.QCanvasCustomBrush.setAnimationRunning` with ``true`` will make this value update automatically every frame, and can be used to drive animated content.

.. _qcanvascustombrush-built-in-shader-inputs-uniforms-and-helper-functions:

Built-in Shader Inputs, Uniforms, and Helper Functions
------------------------------------------------------

The ``QC_INCLUDE`` statement is not a standard preprocessor directive. It is handled by qt_add_custom_brush_shaders() at build time, before the shader is passed to the regular shader compilation pipeline. The statement is replaced by a block of GLSL source code that declares the shader inputs and outputs, the texture samplers, a shared uniform block, and, for fragment shaders, a set of helper functions. Use ``"customvert.glsl"`` in vertex shaders and ``"customfrag.glsl"`` in fragment shaders.

This means that a custom brush shader does not declare these inputs, outputs, samplers, or uniforms itself; they are all made available by the ``QC_INCLUDE`` statement.

.. _qcanvascustombrush-vertex-shader-interface:

Vertex Shader Interface
.......................

A vertex shader that includes ``"customvert.glsl"`` has the following inputs and outputs declared:

* ``in vec2 vertex`` - The vertex position in the canvas coordinate system.

* ``in vec2 tcoord`` - The texture coordinate associated with the vertex.

* ``out vec2 texCoord`` - Forwarded to the fragment shader. Typically set to ``tcoord``.

* ``out vec2 fragCoord`` - Forwarded to the fragment shader. Typically set to ``vertex``.

**Note:** These variables are available implicitly via the ``QC_INCLUDE`` directive. The vertex shader snippet itself must not declare them.

In addition, the following transformation-related uniforms are available:

* ``vec4 viewRect`` - The viewport rectangle, as (x, y, width, height).

* ``int ndcIsYDown`` - Non-zero when the normalized device coordinate system has its Y axis pointing downwards, as is the case with some graphics APIs. Take this into account when computing ``gl_Position``.

* ``mat3 vertMatrix`` - The current transformation matrix.

A vertex shader must write ``gl_Position``, and is expected to forward ``texCoord`` and ``fragCoord`` to the fragment stage.

**Note:** Custom vertex shaders are less common. Most custom brushes are expected to use the default, built-in vertex shader in combination with a custom, application-provided fragment shader.

A typical vertex shader looks like this:

::

    #version 440

    QC_INCLUDE "customvert.glsl"

    void main()
    {
        texCoord = tcoord;
        fragCoord = vertex;
        vec2 v = (vertMatrix * vec3(vertex, 1.0)).xy;
        if (ndcIsYDown != 0)
            gl_Position = vec4(2.0 * (v.x + viewRect.x) / viewRect.z - 1.0,
                               -1.0 + 2.0 * (v.y + viewRect.y) / viewRect.w, 0.0, 1.0);
        else
            gl_Position = vec4(2.0 * (v.x + viewRect.x) / viewRect.z - 1.0,
                               1.0 - 2.0 * (v.y + viewRect.y) / viewRect.w, 0.0, 1.0);
    }

.. _qcanvascustombrush-fragment-shader-interface:

Fragment Shader Interface
.........................

A fragment shader that includes ``"customfrag.glsl"`` has the following inputs and output declared:

* ``in vec2 texCoord`` - The interpolated texture coordinate.

* ``in vec2 fragCoord`` - The interpolated fragment position, in the same coordinate system as the geometry. Commonly used to drive procedural effects.

* ``out vec4 fragColor`` - The resulting fragment color, which the shader must write. The expected output uses premultiplied alpha.

**Note:** These variables are available implicitly via the ``QC_INCLUDE`` directive. The fragment shader snippet itself must not declare them.

Two texture samplers are available:

* ``sampler2D tex`` - The image texture.

* ``sampler2D fontTex`` - The font texture, holding a signed distance field of the glyphs. Relevant when the brush is used to fill text.

The convenience constants ``TAU`` (equal to 2 \* pi) and ``SQRT2`` are also defined.

.. _qcanvascustombrush-common-uniforms:

Common Uniforms
...............

Both vertex and fragment shaders that use ``QC_INCLUDE`` have access to a shared uniform block. The most commonly used members are:

* ``float iTime`` - A time value, in seconds, that is updated every frame while :sip:ref:`~PyQt6.QtCanvasPainter.QCanvasCustomBrush.isAnimationRunning` is ``true``. Use it to drive animations. See :sip:ref:`~PyQt6.QtCanvasPainter.QCanvasCustomBrush.setAnimationRunning`.

* ``vec4 data1``, ``vec4 data2``, ``vec4 data3``, ``vec4 data4`` - Custom data exposed to the shader. Set these from C++ via :sip:ref:`~PyQt6.QtCanvasPainter.QCanvasCustomBrush.setData1`, :sip:ref:`~PyQt6.QtCanvasPainter.QCanvasCustomBrush.setData2`, :sip:ref:`~PyQt6.QtCanvasPainter.QCanvasCustomBrush.setData3`, and :sip:ref:`~PyQt6.QtCanvasPainter.QCanvasCustomBrush.setData4`.

* ``float globalAlpha`` - The painter's current global opacity. Fragment shaders should normally multiply ``fragColor`` by this value.

* ``vec4 colorEffects`` - The active color effect parameters. Normally applied through applyColorEffects() rather than accessed directly.

* ``float fontAlphaMin``, ``float fontAlphaMax`` - The signed distance field thresholds used when antialiasing glyphs.

.. _qcanvascustombrush-fragment-shader-helper-functions:

Fragment Shader Helper Functions
................................

The fragment shader include provides the following helper functions:

* ``float clipMask()`` - Returns the clip (scissor) coverage, in the [0, 1] range, for the current fragment. Multiply ``fragColor`` by this value to honor the painter's clipping.

* ``float antialiasingAlpha()`` - Returns the antialiasing coverage, in the [0, 1] range, derived from ``texCoord``. Multiply ``fragColor`` by this value to get antialiased edges.

* ``float sdfFontAlphaRaw()`` - Returns the raw signed distance field value sampled from ``fontTex`` at ``texCoord``, without antialiasing. Apply ``smoothstep()`` manually as needed.

* ``float sdfFontAlpha()`` - Returns the glyph alpha sampled from ``fontTex`` at ``texCoord``, with the default antialiasing applied based on ``fontAlphaMin`` and ``fontAlphaMax``.

* ``void applyColorEffects(inout vec4 color)`` - Applies the active contrast, brightness, and saturation effects to ``color`` in place.

A typical fragment shader computes ``fragColor``, multiplies it by ``globalAlpha``, optionally multiplies by ``clipMask()`` and ``antialiasingAlpha()`` to support clipping and antialiasing, and finally calls applyColorEffects().

When text is involved, ``sdfFontAlpha()`` should be taken into account too. For example:

::

    #version 440

    QC_INCLUDE "customfrag.glsl"

    void main()
    {
        float a = 0.6 + 0.2 * sin(0.1 * fragCoord.x + 4.0 * iTime);
        vec4 color = vec4(a, a, a, 1.0);
        fragColor = sdfFontAlpha() * globalAlpha * color;
        applyColorEffects(fragColor);
    }

.. _qcanvascustombrush-adding-the-shaders-to-the-project:

Adding the Shaders to the Project
---------------------------------

Shaders that are used with :sip:ref:`~PyQt6.QtCanvasPainter.QCanvasCustomBrush` must always be added to the application project via the `qt_add_custom_brush_shaders <https://doc.qt.io/qt-6/qt-add-custom-brush-shaders.html>`_ CMake function, provided by the Qt Canvas Painter package. This function performs additional preprocessing at build time before internally invoking the standard ``qt_add_shaders()``.

For example:

::

    qt_add_custom_brush_shaders(app "app_custombrush_shaders"
        PREFIX
            "/shaders"
        FILES
            brush1.frag
    )

.. _qcanvascustombrush-using-the-brush:

Using the Brush
---------------

At run time, the generated ``.qsb`` file can be used for example like this:

::

    QCanvasCustomBrush customBrush(":/shaders/brush1.frag.qsb"));
    customBrush.setAnimationRunning(true); // iTime updates automatically
    // expose custom data to the shader in data1
    customBrush.setData1(QVector4D(1.0, 2.0, 3.0, 4.0));

The :sip:ref:`~PyQt6.QtCanvasPainter.QCanvasCustomBrush` can then be used in a fill, for example:

::

    painter->setFillStyle(customBrush);

See `qt_add_custom_brush_shaders <https://doc.qt.io/qt-6/qt-add-custom-brush-shaders.html>`_ for the details of the CMake function, and the Qt Shader Tools module documentation for working with cross-platform shader code in Qt.

**Note:** Shaders for custom brushes must always contain the ``QC_INCLUDE`` statement and must be added to the project via the `qt_add_custom_brush_shaders <https://doc.qt.io/qt-6/qt-add-custom-brush-shaders.html>`_ CMake function. qt_add_shaders() is not suitable for custom brush shaders.

**Note:** qt_add_custom_brush_shaders translates the shader code to the following targets: GLSL ``300 es``, ``150``, ``130``, HLSL ``5.0``, and MSL ``1.2``. There is currently no further configurability offered for this.

.. seealso:: `qt_add_custom_brush_shaders <https://doc.qt.io/qt-6/qt-add-custom-brush-shaders.html>`_, `Qt Canvas Painter - Gallery Example <https://doc.qt.io/qt-6/qtcanvaspainter-gallery-example.html>`_.
