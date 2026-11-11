.. sip:method-description::
    :status: todo
    :pysig: 8b19f06d5e4cdaea09e5db9350708228
    :realsig: (QRhiCommandBuffer*)
    :digest: d85a7b8c1c2465ad577416f6466483cc

Called when the widget contents (i.e. the contents of the texture) need updating.

There is always at least one call to :sip:ref:`~PyQt6.QtWidgets.QRhiWidget.initialize` before this function is called.

To request updates, call :sip:ref:`~PyQt6.QtWidgets.QWidget.update`. Calling update() from within render() will lead to updating continuously, throttled by vsync.

*cb* is the :sip:ref:`~PyQt6.QtGui.QRhiCommandBuffer` for the current frame of the widget. The function is called with a frame being recorded, but without an active render pass.

.. seealso:: :sip:ref:`~PyQt6.QtWidgets.QRhiWidget.initialize`.
