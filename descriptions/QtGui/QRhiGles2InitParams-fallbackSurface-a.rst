.. sip:attribute-description::
    :status: todo
    :digest: fabff71de66825f0626f767ef9c2a01e

A :sip:ref:`~PyQt6.QtGui.QSurface` compatible with format. Typically a :sip:ref:`~PyQt6.QtGui.QOffscreenSurface`. Providing this is mandatory. Be aware of the threading implications: a :sip:ref:`~PyQt6.QtGui.QOffscreenSurface`, like :sip:ref:`~PyQt6.QtGui.QWindow`, must only ever be created and destroyed on the main (gui) thread, even if the :sip:ref:`~PyQt6.QtGui.QRhi` is created and operates on another thread.
