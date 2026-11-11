.. sip:method-description::
    :status: todo
    :pysig: d41d8cd98f00b204e9800998ecf8427e
    :realsig: ()
    :digest: 3a78463982cc59b0be1d7236315e5666

Called when the need to early-release the graphics resources arises.

This normally does not happen for a :sip:ref:`~PyQt6.QtWidgets.QRhiWidget` that is added to a top-level widget's child hierarchy and it then stays there for the rest of its and the top-level's lifetime. Thus in many cases there is no need to reimplement this function, e.g. because the application only ever has a single top-level widget (native window). However, when reparenting of the widget (or an ancestor of it) is involved, reimplementing this function will become necessary in robust, well-written :sip:ref:`~PyQt6.QtWidgets.QRhiWidget` subclasses.

When this function is called, the implementation is expected to destroy all :sip:ref:`~PyQt6.QtGui.QRhi` resources (\ :sip:ref:`~PyQt6.QtGui.QRhiBuffer`, :sip:ref:`~PyQt6.QtGui.QRhiTexture`, etc. objects), similarly to how it is expected to do this in the destructor. Nulling out, using a smart pointer, or setting a ``resources-invalid`` flag is going to be required as well, because :sip:ref:`~PyQt6.QtWidgets.QRhiWidget.initialize` will eventually get called afterwards. Note however that deferring the releasing of resources to the subsequent :sip:ref:`~PyQt6.QtWidgets.QRhiWidget.initialize` is wrong. If this function is called, the resource must be dropped before returning. Also note that implementing this function does not replace the class destructor (or smart pointers): the graphics resources must still be released in both.

See the `Cube RHI Widget Example <https://doc.qt.io/qt-6/qtwidgets-rhi-cuberhiwidget-example.html>`_ for an example of this in action. There the button that toggles the :sip:ref:`~PyQt6.QtWidgets.QRhiWidget` between being a child widget (due to having a parent widget) and being a top-level widget (due to having no parent widget), will trigger invoking this function since the associated top-level widget, native window, and :sip:ref:`~PyQt6.QtGui.QRhi` all change during the lifetime of the :sip:ref:`~PyQt6.QtWidgets.QRhiWidget`, with the previously used :sip:ref:`~PyQt6.QtGui.QRhi` getting destroyed which implies an early-release of the associated resources managed by the still-alive :sip:ref:`~PyQt6.QtWidgets.QRhiWidget`.

Another case when this function is called is when :sip:ref:`~PyQt6.QtWidgets.QRhiWidget.grabFramebuffer` is used with a :sip:ref:`~PyQt6.QtWidgets.QRhiWidget` that is not added to a visible window, i.e. the rendering is performed offscreen. If later on this :sip:ref:`~PyQt6.QtWidgets.QRhiWidget` is made visible, or added to a visible widget hierarchy, the associated :sip:ref:`~PyQt6.QtGui.QRhi` will change from the temporary one used for offscreen rendering to the window's dedicated one, thus triggering this function as well.

.. seealso:: :sip:ref:`~PyQt6.QtWidgets.QRhiWidget.initialize`.
