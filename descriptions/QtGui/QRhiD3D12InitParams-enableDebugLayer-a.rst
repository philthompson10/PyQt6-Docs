.. sip:attribute-description::
    :status: todo
    :digest: cf1b0ec7e2d02a196195fe626f8052e3

When set to true, the debug layer is enabled, if installed and available. The default value is false.

The messages from the debug layer are printed via :sip:ref:`~PyQt6.QtCore.qDebug`, unless the debug layer is too old to support message callbacks, in which case the messages are only sent to the debug output.
