.. sip:method-description::
    :status: todo
    :pysig: 464116456943d857ef223b2d24ec328b
    :realsig: (const QString&)
    :digest: 780712e1bd4d7c7a431af198b5be36ed

Adds *path* as a directory where the engine searches for installed modules in a URL-based directory structure. Qt assumes that all files and folders under *path* come from a trusted source.

The *path* may be a local filesystem directory, a `Qt Resource <https://doc.qt.io/qt-6/resources.html>`_ path (``:/imports``), a `Qt Resource <https://doc.qt.io/qt-6/resources.html>`_ url (``qrc:/imports``) or a URL.

The *path* will be converted into canonical form before it is added to the import path list.

The newly added *path* will be first in the :sip:ref:`~PyQt6.QtQml.QQmlEngine.importPathList`.

**See also** :sip:ref:`~PyQt6.QtQml.QQmlEngine.setImportPathList`, `QML Modules <https://doc.qt.io/qt-6/qtqml-modules-topic.html>`_, and `QML Import Path <https://doc.qt.io/qt-6/qtqml-syntax-imports.html#qml-import-path>`_
