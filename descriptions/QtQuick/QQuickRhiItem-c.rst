.. sip:class-description::
    :status: todo
    :brief: Portable alternative to QQuickFramebufferObject that is not tied to OpenGL, but rather allows integrating rendering with the QRhi APIs with Qt Quick
    :digest: 6ef96f75657a1b708baa8e2f251123b8

The :sip:ref:`~PyQt6.QtQuick.QQuickRhiItem` class is a portable alternative to :sip:ref:`~PyQt6.QtQuick.QQuickFramebufferObject` that is not tied to OpenGL, but rather allows integrating rendering with the :sip:ref:`~PyQt6.QtGui.QRhi` APIs with Qt Quick.

:sip:ref:`~PyQt6.QtQuick.QQuickRhiItem` is effectively the counterpart of :sip:ref:`~PyQt6.QtWidgets.QRhiWidget` in the world of Qt Quick. Both of these are meant to be subclassed, and they both enable recording :sip:ref:`~PyQt6.QtGui.QRhi`-based rendering that targets an offscreen color buffer. The resulting 2D image is then composited with the rest of the Qt Quick scene.

**Note:** While :sip:ref:`~PyQt6.QtQuick.QQuickRhiItem` is a public Qt API, the :sip:ref:`~PyQt6.QtGui.QRhi` family of classes in the Qt Gui module, including :sip:ref:`~PyQt6.QtGui.QShader` and :sip:ref:`~PyQt6.QtGui.QShaderDescription`, offer limited compatibility guarantees. There are no source or binary compatibility guarantees for these classes, meaning the API is only guaranteed to work with the Qt version the application was developed against. Source incompatible changes are however aimed to be kept at a minimum and will only be made in minor releases (6.7, 6.8, and so on). ``qquickrhiitem.h`` does not directly include any :sip:ref:`~PyQt6.QtGui.QRhi`-related headers. To use those classes when implementing a :sip:ref:`~PyQt6.QtQuick.QQuickRhiItem` subclass, link to ``Qt::GuiPrivate`` (if using CMake), and include the appropriate headers with the ``rhi`` prefix, for example ``#include <rhi/qrhi.h>``.

:sip:ref:`~PyQt6.QtQuick.QQuickRhiItem` is a replacement for the legacy :sip:ref:`~PyQt6.QtQuick.QQuickFramebufferObject` class. The latter is inherently tied to OpenGL / OpenGL ES, whereas :sip:ref:`~PyQt6.QtQuick.QQuickRhiItem` works with the :sip:ref:`~PyQt6.QtGui.QRhi` classes, allowing to run the same rendering code with Vulkan, Metal, Direct 3D 11/12, and OpenGL / OpenGL ES. Conceptually and functionally they are very close, and migrating from :sip:ref:`~PyQt6.QtQuick.QQuickFramebufferObject` to :sip:ref:`~PyQt6.QtQuick.QQuickRhiItem` is straightforward. :sip:ref:`~PyQt6.QtQuick.QQuickFramebufferObject` continues to be available to ensure compatibility for existing application code that works directly with the OpenGL API.

**Note:** :sip:ref:`~PyQt6.QtQuick.QQuickRhiItem` will not be functional when using the ``software`` adaptation of the Qt Quick scene graph.

On most platforms, the scene graph rendering, and thus the rendering performed by the :sip:ref:`~PyQt6.QtQuick.QQuickRhiItem` will occur on a `dedicated thread <https://doc.qt.io/qt-6/qtquick-visualcanvas-scenegraph.html#scene-graph-and-rendering>`_. For this reason, the :sip:ref:`~PyQt6.QtQuick.QQuickRhiItem` class enforces a strict separation between the item implementation (the :sip:ref:`~PyQt6.QtQuick.QQuickItem` subclass) and the actual rendering logic. All item logic, such as properties and UI-related helper functions exposed to QML must be located in the :sip:ref:`~PyQt6.QtQuick.QQuickRhiItem` subclass. Everything that relates to rendering must be located in the :sip:ref:`~PyQt6.QtQuick.QQuickRhiItemRenderer` class. To avoid race conditions and read/write issues from two threads it is important that the renderer and the item never read or write shared variables. Communication between the item and the renderer should primarily happen via the QQuickRhiItem::synchronize() function. This function will be called on the render thread while the GUI thread is blocked. Using queued connections or events for communication between item and renderer is also possible.

Applications must subclass both :sip:ref:`~PyQt6.QtQuick.QQuickRhiItem` and :sip:ref:`~PyQt6.QtQuick.QQuickRhiItemRenderer`. The pure virtual :sip:ref:`~PyQt6.QtQuick.QQuickRhiItem.createRenderer` function must be reimplemented to return a new instance of the :sip:ref:`~PyQt6.QtQuick.QQuickRhiItemRenderer` subclass.

As with :sip:ref:`~PyQt6.QtWidgets.QRhiWidget`, :sip:ref:`~PyQt6.QtQuick.QQuickRhiItem` automatically managed the color buffer, which is a 2D texture (\ :sip:ref:`~PyQt6.QtGui.QRhiTexture`) normally, or a :sip:ref:`~PyQt6.QtGui.QRhiRenderBuffer` when multisampling is in use. (some 3D APIs differentiate between textures and renderbuffers, while with some others the underlying native resource is the same; renderbuffers are used mainly to allow multisampling with OpenGL ES 3.0)

The size of the texture will by default adapt to the size of the item (with the :sip:ref:`~PyQt6.QtQuick.QQuickWindow.effectiveDevicePixelRatio` taken into account). If the item size changes, the texture is recreated with the correct size. If a fixed size is preferred, set :sip:ref:`~PyQt6.QtQuick.QQuickRhiItem.fixedColorBufferWidth` and :sip:ref:`~PyQt6.QtQuick.QQuickRhiItem.fixedColorBufferHeight` to non-zero values.

:sip:ref:`~PyQt6.QtQuick.QQuickRhiItem` is a :sip:ref:`~PyQt6.QtQuick.QSGTextureProvider` and can be used directly in `ShaderEffects <https://doc.qt.io/qt-6/qml-qtquick-shadereffect.html>`_ and other classes that consume texture providers.

While not a primary use case, :sip:ref:`~PyQt6.QtQuick.QQuickRhiItem` also allows incorporating rendering code that directly uses a 3D graphics API such as Vulkan, Metal, Direct 3D, or OpenGL. See :sip:ref:`~PyQt6.QtGui.QRhiCommandBuffer.beginExternal` for details on recording native commands within a :sip:ref:`~PyQt6.QtGui.QRhi` render pass, as well as :sip:ref:`~PyQt6.QtGui.QRhiTexture.createFrom` for a way to wrap an existing native texture and then use it with :sip:ref:`~PyQt6.QtGui.QRhi` in a subsequent render pass. See also :sip:ref:`~PyQt6.QtQuick.QQuickGraphicsConfiguration` regarding configuring the native 3D API environment (e.g. device extensions) and note that the :sip:ref:`~PyQt6.QtQuick.QQuickWindow` can be associated with a custom :sip:ref:`~PyQt6.QtGui.QVulkanInstance` by calling :sip:ref:`~PyQt6.QtGui.QWindow.setVulkanInstance` early enough.

**Note:** :sip:ref:`~PyQt6.QtQuick.QQuickRhiItem` always uses the same :sip:ref:`~PyQt6.QtGui.QRhi` instance the :sip:ref:`~PyQt6.QtQuick.QQuickWindow` uses (and by extension, the same OpenGL context, Vulkan device, etc.). To choose which underlying 3D graphics API is used, call :sip:ref:`~PyQt6.QtQuick.QQuickWindow.setGraphicsApi` on the :sip:ref:`~PyQt6.QtQuick.QQuickWindow` early enough. Changing it is not possible once the scene graph has initialized, and all :sip:ref:`~PyQt6.QtQuick.QQuickRhiItem` instances in the scene will render using the same 3D API.

.. _qquickrhiitem-a-simple-example:

A simple example
................

Take the following subclass of :sip:ref:`~PyQt6.QtQuick.QQuickRhiItem`. It is shown here in complete form. It renders a single triangle with a perspective projection, where the triangle is rotated based on the ``angle`` property of the custom item. (meaning it can be driven for example with animations such as `NumberAnimation <https://doc.qt.io/qt-6/qml-qtquick-numberanimation.html>`_ from QML)

.. literalinclude:: ../../../snippets/qtdeclarative-src-quick-doc-snippets-qquickrhiitem-qquickrhiitem_intro.py

It is notable that this simple class is almost exactly the same as the code shown in the :sip:ref:`~PyQt6.QtWidgets.QRhiWidget` introduction. The vertex and fragment shaders are the same as well. These are provided as Vulkan-style GLSL source code and must be processed first by the Qt shader infrastructure first. This is achieved either by running the ``qsb`` command-line tool manually, or by using the qt_add_shaders() function in CMake. The :sip:ref:`~PyQt6.QtQuick.QQuickRhiItem` loads these pre-processed ``.qsb`` files that are shipped with the application. See Qt Shader Tools for more information about Qt's shader translation infrastructure.

``color.vert``

.. literalinclude:: ../../../snippets/qtdeclarative-src-quick-doc-snippets-qquickrhiitem-qquickrhiitem_intro.vert

``color.frag``

.. literalinclude:: ../../../snippets/qtdeclarative-src-quick-doc-snippets-qquickrhiitem-qquickrhiitem_intro.frag

Once exposed to QML (note the ``QML_NAMED_ELEMENT``), our custom item can be instantiated in any scene. (after importing the appropriate ``URI`` specified for `qt_add_qml_module() <https://doc.qt.io/qt-6/qt-add-qml-module.html>`_ in the CMake project)

::

    ExampleRhiItem {
        anchors.fill: parent
        anchors.margins: 10
        NumberAnimation on angle { from: 0; to: 360; duration: 5000; loops: Animation.Infinite }
    }

See `Scene Graph - RHI Texture Item <https://doc.qt.io/qt-6/qtquick-scenegraph-rhitextureitem-example.html>`_ for a more complex example.

.. seealso:: :sip:ref:`~PyQt6.QtQuick.QQuickRhiItemRenderer`, `Scene Graph - RHI Texture Item <https://doc.qt.io/qt-6/qtquick-scenegraph-rhitextureitem-example.html>`_, :sip:ref:`~PyQt6.QtGui.QRhi`, `Scene Graph and Rendering <https://doc.qt.io/qt-6/qtquick-visualcanvas-scenegraph.html#scene-graph-and-rendering>`_.
