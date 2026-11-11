.. sip:method-description::
    :status: todo
    :pysig: 9daeab2db5574297592cfe242f3e4da3
    :realsig: (const void*)
    :digest: dcc01d4d9ca1965ecadaf60076b9fa23

Deregisters the callback with *key*. If no cleanup callback was registered with *key*, the function does nothing. Callbacks registered without a key cannot be removed.

.. seealso:: :sip:ref:`~PyQt6.QtGui.QRhi.addCleanupCallback`.
