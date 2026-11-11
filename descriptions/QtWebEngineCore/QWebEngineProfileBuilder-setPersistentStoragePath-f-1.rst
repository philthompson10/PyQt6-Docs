.. sip:method-description::
    :status: todo
    :pysig: 7d56101db767f1cae6abcbcf151303ae
    :realsig: (const QString&)
    :digest: e2aea81d1433114976e61eaf91c8b477

Sets the path used to store persistent data for the application to *path*. Persistent data includes persistent cookies, HTML5 local storage, and visited links.

By default, this is below QStandardPaths::DataLocation in a QtWebengine/StorageName specific subdirectory.

**Note:** Use :sip:ref:`~PyQt6.QtCore.QStandardPaths.writableLocation`\ (QStandardPaths::DataLocation) to obtain the QStandardPaths::DataLocation path.

.. seealso:: :sip:ref:`~PyQt6.QtWebEngineCore.QWebEngineProfile.persistentStoragePath`, :sip:ref:`~PyQt6.QtCore.QStandardPaths.writableLocation`.
