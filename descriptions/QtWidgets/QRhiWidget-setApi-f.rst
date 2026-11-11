.. sip:method-description::
    :status: todo
    :pysig: 48872040aaa5fd95b5496e471dfa2f10
    :realsig: (QRhiWidget::Api)
    :digest: 1df426d0138a929e3ccf7d8a6fd65efd

Sets the graphics API and :sip:ref:`~PyQt6.QtGui.QRhi` backend to use to *api*.

**Warning:** This function must be called early enough, before the widget is added to a widget hierarchy and displayed on screen. For example, aim to call the function for the subclass constructor. If called too late, the function will have no effect.

The default value depends on the platform: Metal on macOS and iOS, Direct 3D 11 on Windows, OpenGL otherwise.

The *api* can only be set once for the widget and its top-level window, once it is done and takes effect, the window can only use that API and :sip:ref:`~PyQt6.QtGui.QRhi` backend to render. Attempting to set another value, or to add another :sip:ref:`~PyQt6.QtWidgets.QRhiWidget` with a different *api* will not function as expected.

.. seealso:: :sip:ref:`~PyQt6.QtWidgets.QRhiWidget.setColorBufferFormat`, :sip:ref:`~PyQt6.QtWidgets.QRhiWidget.setDebugLayerEnabled`, :sip:ref:`~PyQt6.QtWidgets.QRhiWidget.api`.
