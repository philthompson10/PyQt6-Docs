.. sip:class-description::
    :status: todo
    :brief: Abstract base class that encapsulates the look and feel of a GUI
    :digest: 3c8744ff68e1bade94d458dc40846c3b

The :sip:ref:`~PyQt6.QtWidgets.QStyle` class is an abstract base class that encapsulates the look and feel of a GUI.

Qt contains a set of :sip:ref:`~PyQt6.QtWidgets.QStyle` implementations that match the look of the platforms it supports. The ``windows`` and ``fusion`` styles are built into the Qt Widgets module. The platform styles are style plugins: ``windows11``, which follows the Windows 11 Fluent design, and ``windowsvista`` on Windows, ``macos`` on macOS, and ``android`` on Android. :sip:ref:`~PyQt6.QtWidgets.QStyleFactory` lists the styles that are available at runtime and creates them by name.

Qt's built-in widgets use :sip:ref:`~PyQt6.QtWidgets.QStyle` to perform nearly all of their drawing, ensuring that they look exactly like the equivalent native widgets. The following images show the same form in the ``windows11``, ``windowsvista``, and ``windows`` styles on Windows, and in the ``fusion`` and ``macos`` styles.

+------------------------------------------------------+------------------------------------------------------+-------------------------------------------------+
| .. image:: ../../../images/gallery-windows11.webp    | .. image:: ../../../images/gallery-windowsvista.webp | .. image:: ../../../images/gallery-windows.webp |
|                                                      |                                                      |                                                 |
| Windows 11                                           | Windows Vista                                        | Windows                                         |
+------------------------------------------------------+------------------------------------------------------+-------------------------------------------------+
| .. image:: ../../../images/gallery-fusion-light.webp | .. image:: ../../../images/gallery-fusion-dark.webp  | .. image:: ../../../images/gallery-macos.webp   |
|                                                      |                                                      |                                                 |
| Fusion                                               | Fusion with a dark palette                           | macOS                                           |
+------------------------------------------------------+------------------------------------------------------+-------------------------------------------------+

.. _qstyle-setting-a-style:

Setting a Style
---------------

The style of the entire application can be set using the :sip:ref:`~PyQt6.QtWidgets.QApplication.setStyle` function. It can also be specified by the user of the application, using the ``-style`` command-line option:

.. literalinclude:: ../../../snippets/qtbase-src-widgets-doc-snippets-code-src_gui_styles_qstyle.py
    :lines: 54-54

If no style is specified, Qt will choose the most appropriate style for the user's platform or desktop environment.

A style can also be set on an individual widget using the :sip:ref:`~PyQt6.QtWidgets.QWidget.setStyle` function.

.. _qstyle-choosing-a-styling-approach:

Choosing a Styling Approach
---------------------------

Choose the mechanism that matches how much you want to change:

* To adjust the platform style, subclass :sip:ref:`~PyQt6.QtWidgets.QProxyStyle`.

* To implement a complete custom look, subclass :sip:ref:`~PyQt6.QtWidgets.QCommonStyle`.

* To describe the design declaratively and share it with Qt Quick Controls, use StyleKit and its QStyleKitStyle.

`Styling Approaches for Qt Widgets <https://doc.qt.io/qt-6/qtwidgets-styling-approaches.html>`_ compares these options with `Qt Style Sheets <https://doc.qt.io/qt-6/stylesheet.html>`_ and explains when each is appropriate.

.. _qstyle-developing-style-aware-custom-widgets:

Developing Style-Aware Custom Widgets
-------------------------------------

If you are developing custom widgets and want them to look good on all platforms, you can use :sip:ref:`~PyQt6.QtWidgets.QStyle` functions to perform parts of the widget drawing, such as :sip:ref:`~PyQt6.QtWidgets.QStyle.drawItemText`, :sip:ref:`~PyQt6.QtWidgets.QStyle.drawItemPixmap`, :sip:ref:`~PyQt6.QtWidgets.QStyle.drawPrimitive`, :sip:ref:`~PyQt6.QtWidgets.QStyle.drawControl`, and :sip:ref:`~PyQt6.QtWidgets.QStyle.drawComplexControl`.

Most :sip:ref:`~PyQt6.QtWidgets.QStyle` draw functions take four arguments:

* an enum value specifying which graphical element to draw

* a :sip:ref:`~PyQt6.QtWidgets.QStyleOption` specifying how and where to render that element

* a :sip:ref:`~PyQt6.QtGui.QPainter` that should be used to draw the element

* a :sip:ref:`~PyQt6.QtWidgets.QWidget` on which the drawing is performed (optional)

For example, if you want to draw a focus rectangle on your widget, you can write:

.. literalinclude:: ../../../snippets/qtbase-src-widgets-doc-snippets-styles-styles.py
    :lines: 66-80

:sip:ref:`~PyQt6.QtWidgets.QStyle` gets all the information it needs to render the graphical element from :sip:ref:`~PyQt6.QtWidgets.QStyleOption`. The widget is passed as the last argument in case the style needs it to perform special effects (such as animated default buttons on macOS), but it isn't mandatory. In fact, you can use :sip:ref:`~PyQt6.QtWidgets.QStyle` to draw on any paint device, not just widgets, by setting the :sip:ref:`~PyQt6.QtGui.QPainter` properly.

:sip:ref:`~PyQt6.QtWidgets.QStyleOption` has various subclasses for the various types of graphical elements that can be drawn. For example, :sip:ref:`~PyQt6.QtWidgets.QStyle.PrimitiveElement.PE_FrameFocusRect` expects a :sip:ref:`~PyQt6.QtWidgets.QStyleOptionFocusRect` argument.

To ensure that drawing operations are as fast as possible, :sip:ref:`~PyQt6.QtWidgets.QStyleOption` and its subclasses have public data members. See the :sip:ref:`~PyQt6.QtWidgets.QStyleOption` class documentation for details on how to use it.

For convenience, Qt provides the :sip:ref:`~PyQt6.QtWidgets.QStylePainter` class, which combines a :sip:ref:`~PyQt6.QtWidgets.QStyle`, a :sip:ref:`~PyQt6.QtGui.QPainter`, and a :sip:ref:`~PyQt6.QtWidgets.QWidget`. This makes it possible to write

.. literalinclude:: ../../../snippets/qtbase-src-widgets-doc-snippets-styles-styles.py
    :lines: 87-87

.. literalinclude:: ../../../snippets/qtbase-src-widgets-doc-snippets-styles-styles.py
    :lines: 95-95

instead of

.. literalinclude:: ../../../snippets/qtbase-src-widgets-doc-snippets-styles-styles.py
    :lines: 70-70

.. literalinclude:: ../../../snippets/qtbase-src-widgets-doc-snippets-styles-styles.py
    :lines: 78-78

.. _qstyle-creating-a-custom-style:

Creating a Custom Style
-----------------------

You can create a custom look and feel for your application by creating a custom style. There are two approaches. To change selected aspects of an existing style, subclass :sip:ref:`~PyQt6.QtWidgets.QProxyStyle` and reimplement the virtual functions that draw or measure the elements you want to change; the proxy forwards everything else to the style it wraps, by default the platform style. To implement a complete look, subclass :sip:ref:`~PyQt6.QtWidgets.QCommonStyle`, which implements the behavior that all of Qt's styles share and leaves the drawing to you. Qt's built-in styles are not part of the public API and cannot serve as base classes; wrap them with :sip:ref:`~PyQt6.QtWidgets.QProxyStyle` instead.

Depending on which parts of the base style you want to change, you must reimplement the functions that are used to draw those parts of the interface. To illustrate this, we will modify the look of the spin box arrows drawn by the platform style. The arrows are *primitive elements* that are drawn by the :sip:ref:`~PyQt6.QtWidgets.QStyle.drawPrimitive` function, so we need to reimplement that function. We need the following class declaration:

.. literalinclude:: ../../../snippets/qtbase-src-widgets-doc-snippets-customstyle-customstyle.py
    :lines: 59-69

To draw its up and down arrows, :sip:ref:`~PyQt6.QtWidgets.QSpinBox` uses the :sip:ref:`~PyQt6.QtWidgets.QStyle.PrimitiveElement.PE_IndicatorSpinUp` and :sip:ref:`~PyQt6.QtWidgets.QStyle.PrimitiveElement.PE_IndicatorSpinDown` primitive elements. Here's how to reimplement the :sip:ref:`~PyQt6.QtWidgets.QStyle.drawPrimitive` function to draw them differently:

.. literalinclude:: ../../../snippets/qtbase-src-widgets-doc-snippets-customstyle-customstyle.py

Notice that we don't use the ``widget`` argument, except to pass it on to the :sip:ref:`~PyQt6.QtWidgets.QProxyStyle.drawPrimitive` function. As mentioned earlier, the information about what is to be drawn and how it should be drawn is specified by a :sip:ref:`~PyQt6.QtWidgets.QStyleOption` object, so there is no need to ask the widget.

If you need to use the ``widget`` argument to obtain additional information, be careful to ensure that it isn't 0 and that it is of the correct type before using it. For example:

.. literalinclude:: ../../../snippets/qtbase-src-widgets-doc-snippets-customstyle-customstyle.py
    :lines: 59-69

When implementing a custom style, you cannot assume that the widget is a :sip:ref:`~PyQt6.QtWidgets.QSpinBox` just because the enum value is called :sip:ref:`~PyQt6.QtWidgets.QStyle.PrimitiveElement.PE_IndicatorSpinUp` or :sip:ref:`~PyQt6.QtWidgets.QStyle.PrimitiveElement.PE_IndicatorSpinDown`.

.. _qstyle-using-a-custom-style:

Using a Custom Style
--------------------

There are several ways of using a custom style in a Qt application. The simplest way is to pass the custom style to the :sip:ref:`~PyQt6.QtWidgets.QApplication.setStyle` static function before creating the :sip:ref:`~PyQt6.QtWidgets.QApplication` object:

.. literalinclude:: ../../../snippets/qtbase-src-widgets-doc-snippets-customstyle-main.py
    :lines: 54-65

You can call :sip:ref:`~PyQt6.QtWidgets.QApplication.setStyle` at any time, but by calling it before the constructor, you ensure that the user's preference, set using the ``-style`` command-line option, is respected.

You may want to make your custom style available for use in other applications, which may not be yours and hence not available for you to recompile. The Qt Plugin system makes it possible to create styles as plugins. Styles created as plugins are loaded as shared objects at runtime by Qt itself. Please refer to the Qt Plugin documentation for more information on how to go about creating a style plugin.

Compile your plugin and put it into Qt's ``plugins/styles`` directory. We now have a pluggable style that Qt can load automatically. To use your new style with existing applications, simply start the application with the following argument:

.. literalinclude:: ../../../snippets/qtbase-src-widgets-doc-snippets-code-src_gui_styles_qstyle.py
    :lines: 59-59

The application will use the look and feel from the custom style you implemented.

.. _qstyle-right-to-left-desktops:

Right-to-Left Desktops
----------------------

Languages written from right to left (such as Arabic and Hebrew) usually also mirror the whole layout of widgets, and require the light to come from the screen's top-right corner instead of top-left.

If you create a custom style, you should take special care when drawing asymmetric elements to make sure that they also look correct in a mirrored layout. An easy way to test your styles is to run applications with the ``-reverse`` command-line option or to call QApplication::setLayoutDirection() in your ``main()`` function.

Here are some things to keep in mind when making a style work well in a right-to-left environment:

* :sip:ref:`~PyQt6.QtWidgets.QStyle.subControlRect` and :sip:ref:`~PyQt6.QtWidgets.QStyle.subElementRect` return rectangles in screen coordinates

* QStyleOption::direction indicates in which direction the item should be drawn in

* If a style is not right-to-left aware it will display items as if it were left-to-right

* :sip:ref:`~PyQt6.QtWidgets.QStyle.visualRect`, :sip:ref:`~PyQt6.QtWidgets.QStyle.visualPos`, and :sip:ref:`~PyQt6.QtWidgets.QStyle.visualAlignment` are helpful functions that will translate from logical to screen representations.

* :sip:ref:`~PyQt6.QtWidgets.QStyle.alignedRect` will return a logical rect aligned for the current direction

.. _qstyle-styles-in-item-views:

Styles in Item Views
--------------------

The painting of items in views is performed by a delegate. Qt's default delegate, :sip:ref:`~PyQt6.QtWidgets.QStyledItemDelegate`, is also used for calculating bounding rectangles of items, and their sub-elements for the various kind of item :sip:ref:`~PyQt6.QtCore.Qt.ItemDataRole` :sip:ref:`~PyQt6.QtWidgets.QStyledItemDelegate` supports. See the :sip:ref:`~PyQt6.QtWidgets.QStyledItemDelegate` class description to find out which datatypes and roles are supported. You can read more about item data roles in `Model/View Programming <https://doc.qt.io/qt-6/model-view-programming.html>`_.

When :sip:ref:`~PyQt6.QtWidgets.QStyledItemDelegate` paints its items, it draws :sip:ref:`~PyQt6.QtWidgets.QStyle.ControlElement.CE_ItemViewItem`, and calculates their size with :sip:ref:`~PyQt6.QtWidgets.QStyle.ContentsType.CT_ItemViewItem`. Note also that it uses :sip:ref:`~PyQt6.QtWidgets.QStyle.SubElement.SE_ItemViewItemText` to set the size of editors. When implementing a style to customize drawing of item views, you need to check the implementation of :sip:ref:`~PyQt6.QtWidgets.QCommonStyle` (and any other subclasses from which your style inherits). This way, you find out which and how other style elements are painted, and you can then reimplement the painting of elements that should be drawn differently.

We include a small example where we customize the drawing of item backgrounds.

.. literalinclude:: ../../../snippets/qtbase-src-widgets-doc-snippets-customviewstyle-customviewstyle.py

The primitive element :sip:ref:`~PyQt6.QtWidgets.QStyle.PrimitiveElement.PE_PanelItemViewItem` is responsible for painting the background of items, and is called from :sip:ref:`~PyQt6.QtWidgets.QCommonStyle`'s implementation of :sip:ref:`~PyQt6.QtWidgets.QStyle.ControlElement.CE_ItemViewItem`.

To add support for drawing of new datatypes and item data roles, it is necessary to create a custom delegate. But if you only need to support the datatypes implemented by the default delegate, a custom style does not need an accompanying delegate. The :sip:ref:`~PyQt6.QtWidgets.QStyledItemDelegate` class description gives more information on custom delegates.

The drawing of item view headers is also done by the style, giving control over size of header items and row and column sizes.

.. seealso:: :sip:ref:`~PyQt6.QtWidgets.QStyleOption`, :sip:ref:`~PyQt6.QtWidgets.QStylePainter`, `Styles and Style Aware Widgets <https://doc.qt.io/qt-6/style-reference.html>`_, `Styling Approaches for Qt Widgets <https://doc.qt.io/qt-6/qtwidgets-styling-approaches.html>`_, :sip:ref:`~PyQt6.QtWidgets.QStyledItemDelegate`, `Styling <https://doc.qt.io/qt-6/qwidget-styling.html>`_.
