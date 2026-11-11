.. sip:method-description::
    :status: todo
    :pysig: 52e9a692a8ce9839eb3548caf86233d1
    :realsig: (QRhi::Implementation, QRhiInitParams*)
    :digest: 1a5ee77c291aed6b4915d6853a685d92

Returns true if :sip:ref:`~PyQt6.QtGui.QRhi.create` can be expected to succeed when called the given *impl* and *params*.

For some backends this is equivalent to calling :sip:ref:`~PyQt6.QtGui.QRhi.create`, checking its return value, and then destroying the resulting :sip:ref:`~PyQt6.QtGui.QRhi`.

For others, in particular with Metal, there may be a specific probing implementation, which allows testing in a more lightweight manner without polluting the debug output with warnings upon failures.

.. seealso:: :sip:ref:`~PyQt6.QtGui.QRhi.create`.
