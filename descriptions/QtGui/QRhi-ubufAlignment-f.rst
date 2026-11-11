.. sip:method-description::
    :status: todo
    :pysig: fa7153f7ed1cb6c0fcf2ffb2fac21748
    :realsig: () const
    :digest: 6d9018e9dec525dfe77a3baadc04463d

Returns the minimum uniform buffer offset alignment in bytes. This is typically 256.

Attempting to bind a uniform buffer region with an offset not aligned to this value will lead to failures depending on the backend and the underlying graphics API.

.. seealso:: :sip:ref:`~PyQt6.QtGui.QRhi.ubufAligned`.
