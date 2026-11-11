.. sip:method-description::
    :status: todo
    :pysig: 93c65966a7252879a2fdbc87264c9da8
    :realsig: (int, int, int, int)
    :digest: 23454688b4581a11d1449222c9112179

Constructs a scissor with the rectangle specified by *x*, *y*, *w*, and *h*.

**Note:** *x* and *y* are assumed to be the bottom-left position. Negative *w* or *h* are not allowed, such scissor rectangles will be ignored by :sip:ref:`~PyQt6.QtGui.QRhiCommandBuffer`. Other than that, the flexible OpenGL semantics apply: negative x and y, partially out of bounds rectangles, etc. will be handled gracefully, clamping as appropriate.
