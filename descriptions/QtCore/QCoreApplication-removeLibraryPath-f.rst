.. sip:method-description::
    :status: todo
    :pysig: db547d59f57d25909df4080d41fbf34a
    :realsig: (const QString&)
    :digest: c9dac78e381dae621f403f544e7c663b

Removes *path* from the library path list. If *path* is empty or not in the path list, the list is not changed.

The library paths are reset to the default when an instance of :sip:ref:`~PyQt6.QtCore.QCoreApplication` is destructed.

**Warning:** :sip:ref:`~PyQt6.QtCore.QLibrary` does not currently use :sip:ref:`~PyQt6.QtCore.QCoreApplication.libraryPaths` to look up non-absolute library paths.

.. seealso:: :sip:ref:`~PyQt6.QtCore.QCoreApplication.addLibraryPath`, :sip:ref:`~PyQt6.QtCore.QCoreApplication.libraryPaths`, :sip:ref:`~PyQt6.QtCore.QCoreApplication.setLibraryPaths`.
