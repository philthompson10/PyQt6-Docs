.. sip:signal-description::
    :status: todo
    :pysig: d41d8cd98f00b204e9800998ecf8427e
    :realsig: ()
    :digest: 99f2a44aea1a960190bea0827959f932

This signal is emitted whenever the widget is supposed to render to its backing texture (either due to a :sip:ref:`~PyQt6.QtWidgets.QWidget.update` or due to a call to :sip:ref:`~PyQt6.QtWidgets.QRhiWidget.grabFramebuffer`), but there is no :sip:ref:`~PyQt6.QtGui.QRhi` for the widget to use, likely due to issues related to graphics configuration.

This signal may be emitted multiple times when a problem arises. Do not assume it is emitted only once. Connect with :sip:ref:`~PyQt6.QtCore.Qt.ConnectionType.SingleShotConnection` if the error handling code is to be notified only once.
