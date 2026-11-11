.. sip:method-description::
    :status: todo
    :pysig: 8178fb7a2bc19599a49657203b225d43
    :realsig: (float, float, float, float, float, float)
    :digest: 6817d8bdf7ff7e1f9106c6393ccc952d

Constructs a viewport description with the rectangle specified by *x*, *y*, *w*, *h* and the depth range *minDepth* and *maxDepth*.

**Note:** *x* and *y* are assumed to be the bottom-left position. *w* and *h* should not be negative, the viewport will be ignored by :sip:ref:`~PyQt6.QtGui.QRhiCommandBuffer.setViewport` otherwise.

.. seealso:: :sip:ref:`~PyQt6.QtGui.QRhi.clipSpaceCorrMatrix`.
