.. sip:class-description::
    :status: todo
    :brief: Widget for rendering 3D graphics via an accelerated grapics API, such as Vulkan, Metal, or Direct 3D
    :digest: afe545b6650539a2cd24f8f41ab79504

The :sip:ref:`~PyQt6.QtWidgets.QRhiWidget` class is a widget for rendering 3D graphics via an accelerated grapics API, such as Vulkan, Metal, or Direct 3D.

:sip:ref:`~PyQt6.QtWidgets.QRhiWidget` provides functionality for displaying 3D content rendered through the :sip:ref:`~PyQt6.QtGui.QRhi` APIs within a :sip:ref:`~PyQt6.QtWidgets.QWidget`-based application. In many ways it is the portable equivalent of :sip:ref:`~PyQt6.QtOpenGLWidgets.QOpenGLWidget` that is not tied to a single 3D graphics API, but rather can function with all the APIs :sip:ref:`~PyQt6.QtGui.QRhi` supports (such as, Direct 3D 11/12, Vulkan, Metal, and OpenGL).

:sip:ref:`~PyQt6.QtWidgets.QRhiWidget` is expected to be subclassed. To render into the 2D texture that is implicitly created and managed by the :sip:ref:`~PyQt6.QtWidgets.QRhiWidget`, subclasses should reimplement the virtual functions :sip:ref:`~PyQt6.QtWidgets.QRhiWidget.initialize` and :sip:ref:`~PyQt6.QtWidgets.QRhiWidget.render`.

The size of the texture will by default adapt to the size of the widget. If a fixed size is preferred, set a fixed size specified in pixels by calling :sip:ref:`~PyQt6.QtWidgets.QRhiWidget.setFixedColorBufferSize`.

In addition to the texture serving as the color buffer, a depth/stencil buffer and a render target binding these together is maintained implicitly as well.

The :sip:ref:`~PyQt6.QtGui.QRhi` for the widget's top-level window is configured to use a platform-specific backend and graphics API by default: Metal on macOS and iOS, Direct 3D 11 on Windows, OpenGL otherwise. Call :sip:ref:`~PyQt6.QtWidgets.QRhiWidget.setApi` to override this.

**Note:** A single widget window can only use one :sip:ref:`~PyQt6.QtGui.QRhi` backend, and so one single 3D graphics API. If two :sip:ref:`~PyQt6.QtWidgets.QRhiWidget` or :sip:ref:`~PyQt6.QtQuickWidgets.QQuickWidget` widgets in the window's widget hierarchy request different APIs, only one of them will function correctly.

**Note:** While :sip:ref:`~PyQt6.QtWidgets.QRhiWidget` is a public Qt API, the :sip:ref:`~PyQt6.QtGui.QRhi` family of classes in the Qt Gui module, including :sip:ref:`~PyQt6.QtGui.QRhi`, :sip:ref:`~PyQt6.QtGui.QShader` and :sip:ref:`~PyQt6.QtGui.QShaderDescription`, offer limited compatibility guarantees. There are no source or binary compatibility guarantees for these classes, meaning the API is only guaranteed to work with the Qt version the application was developed against. Source incompatible changes are however aimed to be kept at a minimum and will only be made in minor releases (6.7, 6.8, and so on). ``qrhiwidget.h`` does not directly include any :sip:ref:`~PyQt6.QtGui.QRhi`-related headers. To use those classes when implementing a :sip:ref:`~PyQt6.QtWidgets.QRhiWidget` subclass, link to ``Qt::GuiPrivate`` (if using CMake), and include the appropriate headers with the ``rhi`` prefix, for example ``#include <rhi/qrhi.h>``.

An example of a simple :sip:ref:`~PyQt6.QtWidgets.QRhiWidget` subclass rendering a triangle is the following:

.. literalinclude:: ../../../snippets/qtbase-src-widgets-doc-snippets-qrhiwidget-rhiwidgetintro.py

This is a widget that continuously requests updates, throttled by the presentation rate (vsync, depending on the screen refresh rate). If rendering continuously is not desired, the update() call in :sip:ref:`~PyQt6.QtWidgets.QRhiWidget.render` should be removed, and rather issued only when updating the rendered content is necessary. For example, if the rotation of the cube should be tied to the value of a :sip:ref:`~PyQt6.QtWidgets.QSlider`, then connecting the slider's value change signal to a slot or lambda that forwards the new value and calls update() is sufficient.

The vertex and fragment shaders are provided as Vulkan-style GLSL and must be processed first by the Qt shader infrastructure first. This is achieved either by running the ``qsb`` command-line tool manually, or by using the qt_add_shaders() function in CMake. The :sip:ref:`~PyQt6.QtWidgets.QRhiWidget` implementation loads these pre-processed ``.qsb`` files that are shipped with the application. See Qt Shader Tools for more information about Qt's shader translation infrastructure.

The source code for these shaders could be the following:

``color.vert``

.. literalinclude:: ../../../snippets/qtbase-src-widgets-doc-snippets-qrhiwidget-rhiwidgetintro.vert

``color.frag``

.. literalinclude:: ../../../snippets/qtbase-src-widgets-doc-snippets-qrhiwidget-rhiwidgetintro.frag

The result is a widget that shows the following:

.. image:: ../../../images/qrhiwidget-intro.jpg

For a complete, minimal, introductory example check out the `Simple RHI Widget Example <https://doc.qt.io/qt-6/qtwidgets-rhi-simplerhiwidget-example.html>`_.

For an example with more functionality and demonstration of further concepts, see the `Cube RHI Widget Example <https://doc.qt.io/qt-6/qtwidgets-rhi-cuberhiwidget-example.html>`_.

:sip:ref:`~PyQt6.QtWidgets.QRhiWidget` always involves rendering into a backing texture, not directly to the window (the surface or layer provided by the windowing system for the native window). This allows properly compositing the content with the rest of the widget-based UI, and offering a simple and compact API, making it easy to get started. All this comes at the expense of additional resources and a potential effect on performance. This is often perfectly acceptable in practice, but advanced users should keep in mind the pros and cons of the different approaches. Refer to the `RHI Window Example <https://doc.qt.io/qt-6/qtgui-rhiwindow-example.html>`_ and compare it with the `Simple RHI Widget Example <https://doc.qt.io/qt-6/qtwidgets-rhi-simplerhiwidget-example.html>`_ for details about the two approaches.

Reparenting a :sip:ref:`~PyQt6.QtWidgets.QRhiWidget` into a widget hierarchy that belongs to a different window (top-level widget), or making the :sip:ref:`~PyQt6.QtWidgets.QRhiWidget` itself a top-level (by setting the parent to ``nullptr``), involves changing the associated :sip:ref:`~PyQt6.QtGui.QRhi` (and potentially destroying the old one) while the :sip:ref:`~PyQt6.QtWidgets.QRhiWidget` continues to stay alive and well. To support this, robust :sip:ref:`~PyQt6.QtWidgets.QRhiWidget` implementations are expected to reimplement the :sip:ref:`~PyQt6.QtWidgets.QRhiWidget.releaseResources` virtual function as well, and drop their :sip:ref:`~PyQt6.QtGui.QRhi` resources just as they do in the destructor. The `Cube RHI Widget Example <https://doc.qt.io/qt-6/qtwidgets-rhi-cuberhiwidget-example.html>`_ demonstrates this in practice.

While not a primary use case, :sip:ref:`~PyQt6.QtWidgets.QRhiWidget` also allows incorporating rendering code that directly uses a 3D graphics API such as Vulkan, Metal, Direct 3D, or OpenGL. See :sip:ref:`~PyQt6.QtGui.QRhiCommandBuffer.beginExternal` for details on recording native commands within a :sip:ref:`~PyQt6.QtGui.QRhi` render pass, as well as :sip:ref:`~PyQt6.QtGui.QRhiTexture.createFrom` for a way to wrap an existing native texture and then use it with :sip:ref:`~PyQt6.QtGui.QRhi` in a subsequent render pass. Note however that the configurability of the underlying graphics API (its device or context features, layers, extensions, etc.) is going to be limited since :sip:ref:`~PyQt6.QtWidgets.QRhiWidget`'s primary goal is to provide an environment suitable for :sip:ref:`~PyQt6.QtGui.QRhi`-based rendering code, not to enable arbitrary, potentially complex, foreign rendering engines.

.. seealso:: :sip:ref:`~PyQt6.QtGui.QRhi`, :sip:ref:`~PyQt6.QtGui.QShader`, :sip:ref:`~PyQt6.QtOpenGLWidgets.QOpenGLWidget`, `Simple RHI Widget Example <https://doc.qt.io/qt-6/qtwidgets-rhi-simplerhiwidget-example.html>`_, `Cube RHI Widget Example <https://doc.qt.io/qt-6/qtwidgets-rhi-cuberhiwidget-example.html>`_.
