.. sip:method-description::
    :status: todo
    :pysig: 46a7bdf6ff0ff3a292573662f7d8a6a2
    :realsig: (const QUrl&)
    :digest: 58e06102651ddf9a33081d7b04cb4002

Saves the contents to the file and format specified by *url*.

The file extension in *url* specifies the file format (as determined by :sip:ref:`~PyQt6.QtCore.QMimeDatabase.mimeTypeForUrl`).

**Note:** You can save to a local file, or on Android to a ``content`` URL.

.. seealso:: :sip:ref:`~PyQt6.QtQuick.QQuickTextDocument.source`, :sip:ref:`~PyQt6.QtQuick.QQuickTextDocument.save`.
