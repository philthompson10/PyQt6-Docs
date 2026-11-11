.. sip:method-description::
    :status: todo
    :pysig: 252f2463b17d7b65060495677c920d4c
    :realsig: (const QStringList&)
    :digest: f6f7cfe87e01281b9c47cde897806e1c

Sets *paths* as the list of directories where the engine searches for installed modules in a URL-based directory structure. Qt assumes that all files and folders under *paths* come from a trusted source.

By default, this list contains the paths mentioned in `QML Import Path <https://doc.qt.io/qt-6/qtqml-syntax-imports.html#qml-import-path>`_.

**Warning:** Calling setImportPathList does not preserve the default import paths.

.. seealso:: :sip:ref:`~PyQt6.QtQml.QQmlEngine.importPathList`, :sip:ref:`~PyQt6.QtQml.QQmlEngine.addImportPath`.
