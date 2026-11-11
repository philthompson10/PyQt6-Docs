.. sip:method-description::
    :status: todo
    :pysig: db547d59f57d25909df4080d41fbf34a
    :realsig: (const QString&)
    :digest: da1186fa095a6e400ffca2ea1c387cdf

Prepends *path* to the beginning of the library path list, ensuring that it is searched for libraries first. If *path* is empty or already in the path list, the path list is not changed.

The default path list consists of one or two entries. The first is the installation directory for plugins, which is ``INSTALL/plugins``, where ``INSTALL`` is the directory where Qt was installed. The second is the application's own directory (\ **not** the current directory), but only after the :sip:ref:`~PyQt6.QtCore.QCoreApplication` object is instantiated.

The library paths are reset to the default when an instance of :sip:ref:`~PyQt6.QtCore.QCoreApplication` is destructed.

**Warning:** :sip:ref:`~PyQt6.QtCore.QLibrary` does not currently use the given path to look up non-absolute library paths.

.. seealso:: :sip:ref:`~PyQt6.QtCore.QCoreApplication.removeLibraryPath`, :sip:ref:`~PyQt6.QtCore.QCoreApplication.libraryPaths`, :sip:ref:`~PyQt6.QtCore.QCoreApplication.setLibraryPaths`.
