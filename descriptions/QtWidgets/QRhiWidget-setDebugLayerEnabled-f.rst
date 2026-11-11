.. sip:method-description::
    :status: todo
    :pysig: c506ff134babdd6e68ab3e6350e95305
    :realsig: (bool)
    :digest: cf424163c4a4f980a3573d7de1a8c595

Requests the debug or validation layer of the underlying graphics API when *enable* is true.

**Warning:** This function must be called early enough, before the widget is added to a widget hierarchy and displayed on screen. For example, aim to call the function for the subclass constructor. If called too late, the function will have no effect.

Applicable for Vulkan and Direct 3D.

By default this is disabled.

.. seealso:: :sip:ref:`~PyQt6.QtWidgets.QRhiWidget.setApi`, :sip:ref:`~PyQt6.QtWidgets.QRhiWidget.isDebugLayerEnabled`.
