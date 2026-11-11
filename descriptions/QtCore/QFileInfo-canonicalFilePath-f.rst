.. sip:method-description::
    :status: todo
    :pysig: 341be97d9aff90c9978347f66f945b77
    :realsig: () const
    :digest: 29c3031be743d767d747e1c1b7066057

Returns the file system entry's canonical path, including the entry's name, that is, an absolute path without symbolic links or redundant ``'.'`` or ``'..'`` elements.

This method returns an empty string if the entry does not exist, is not reachable (for example, the current user does not have access to a directory path), or an error occurs while canonicalizing the path (normally due to dangling symbolic links).

.. seealso:: :sip:ref:`~PyQt6.QtCore.QFileInfo.filePath`, :sip:ref:`~PyQt6.QtCore.QFileInfo.absoluteFilePath`, :sip:ref:`~PyQt6.QtCore.QFileInfo.dir`.
