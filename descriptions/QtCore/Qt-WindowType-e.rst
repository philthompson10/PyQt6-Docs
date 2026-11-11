.. sip:enum-description::
    :status: todo
    :digest: cf28e3a65b0792196ad0e2450f79c792

This enum type is used to specify various window-system properties for the widget. They are fairly unusual but necessary in a few cases. Some of these flags depend on whether the underlying window manager supports them.

The main types are

There are also a number of flags which you can use to customize the appearance of top-level windows. These have no effect on other windows:

On X11, the result of the flag is dependent on the window manager and its ability to understand Motif and/or NETWM hints. Most existing modern window managers can handle this.

**Note:** If the window manager relies on the frame to interactively manipulate the window, the user can no longer move or resize the window via the window system, but this side effect should not be relied on. To produce a fixed size window that can not be resized, please set :sip:ref:`~PyQt6.QtGui.QWindow.setMinimumSize` and :sip:ref:`~PyQt6.QtGui.QWindow.setMaximumSize` to the same size.

The ``CustomizeWindowHint`` flag is used to enable customization of the window controls. This flag must be set to allow the ``WindowTitleHint``, ``WindowSystemMenuHint``, ``WindowMinimizeButtonHint``, ``WindowMaximizeButtonHint`` and ``WindowCloseButtonHint`` flags to be changed.

.. seealso:: :sip:ref:`~PyQt6.QtWidgets.QWidget.windowFlags`, `Window Flags Example <https://doc.qt.io/qt-6/qtwidgets-widgets-windowflags-example.html>`_.
