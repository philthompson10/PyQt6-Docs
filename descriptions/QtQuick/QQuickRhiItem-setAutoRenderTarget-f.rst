.. sip:method-description::
    :status: todo
    :pysig: c506ff134babdd6e68ab3e6350e95305
    :realsig: (bool)
    :digest: d065d6707e67cc5536f7e39d2d7588dc

Controls if a depth-stencil :sip:ref:`~PyQt6.QtGui.QRhiRenderBuffer` and a :sip:ref:`~PyQt6.QtGui.QRhiTextureRenderTarget` is created and maintained automatically by the item. The default value is ``true``. Call this function early on, for example from the derived class' constructor, with *enabled* set to ``false`` to disable this.

In automatic mode, the size and sample count of the depth-stencil buffer follows the color buffer texture's settings. In non-automatic mode, renderTarget() and depthStencilBuffer() always return ``nullptr`` and it is then up to the application's implementation of initialize() to take care of setting up and managing these objects.
