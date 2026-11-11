.. sip:method-description::
    :status: todo
    :pysig: c506ff134babdd6e68ab3e6350e95305
    :realsig: (bool)
    :digest: 1c7b528cb943cc96afff4358a8153b37

Controls if a depth-stencil :sip:ref:`~PyQt6.QtGui.QRhiRenderBuffer` and a :sip:ref:`~PyQt6.QtGui.QRhiTextureRenderTarget` is created and maintained automatically by the widget. The default value is ``true``.

In automatic mode, the size and sample count of the depth-stencil buffer follows the color buffer texture's settings. In non-automatic mode, :sip:ref:`~PyQt6.QtWidgets.QRhiWidget.renderTarget` and :sip:ref:`~PyQt6.QtWidgets.QRhiWidget.depthStencilBuffer` always return ``nullptr`` and it is then up to the application's implementation of :sip:ref:`~PyQt6.QtWidgets.QRhiWidget.initialize` to take care of setting up and managing these objects.

Call this function with *enabled* set to ``false`` early on, for example in the derived class' constructor, to disable the automatic mode.
