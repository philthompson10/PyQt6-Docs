.. sip:method-description::
    :status: todo
    :pysig: 046214a63eb654b19756ff29ac5e88bc
    :realsig: (const QStringList&)
    :digest: 8ba581afea14aa8e15d5b1b67756ddf3

Sets the list of directories to search when loading plugins with :sip:ref:`~PyQt6.QtCore.QLibrary` to *paths*. All existing paths will be deleted and the path list will consist of the paths given in *paths* and the path to the application.

The library paths are reset to the default when an instance of :sip:ref:`~PyQt6.QtCore.QCoreApplication` is destructed.

**Warning:** :sip:ref:`~PyQt6.QtCore.QLibrary` does not currently use the given paths to look up non-absolute library paths.

.. seealso:: :sip:ref:`~PyQt6.QtCore.QCoreApplication.libraryPaths`, :sip:ref:`~PyQt6.QtCore.QCoreApplication.addLibraryPath`, :sip:ref:`~PyQt6.QtCore.QCoreApplication.removeLibraryPath`, :sip:ref:`~PyQt6.QtCore.QLibrary`.
