.. sip:method-description::
    :status: todo
    :pysig: 341be97d9aff90c9978347f66f945b77
    :realsig: () const
    :digest: a26f77948d5ddc0f1fbea4c421759189

Returns the path used to store persistent data for the profile.

Persistent data includes persistent cookies, HTML5 local storage, and visited links.

By default, this is below QStandardPaths::DataLocation in a QtWebengine/StorageName specific subdirectory.

**Note:** Use :sip:ref:`~PyQt6.QtCore.QStandardPaths.writableLocation`\ (QStandardPaths::DataLocation) to obtain the QStandardPaths::DataLocation path.

.. seealso:: :sip:ref:`~PyQt6.QtWebEngineCore.QWebEngineProfile.setPersistentStoragePath`, :sip:ref:`~PyQt6.QtWebEngineCore.QWebEngineProfile.storageName`, :sip:ref:`~PyQt6.QtCore.QStandardPaths.writableLocation`.
