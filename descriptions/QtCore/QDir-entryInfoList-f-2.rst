.. sip:method-description::
    :status: todo
    :pysig: 2c857d654c4ba96cd8bcdef47e707843
    :realsig: (const QStringList&, QDir::Filters, QDir::SortFlags) const
    :digest: 50faded0ac512b70f4bc67383ca2e12c

Returns a list of :sip:ref:`~PyQt6.QtCore.QFileInfo` objects for all the files and directories in the directory, ordered according to the name and attribute filters previously set with :sip:ref:`~PyQt6.QtCore.QDir.setNameFilters` and :sip:ref:`~PyQt6.QtCore.QDir.setFilter`, and sorted according to the flags set with :sip:ref:`~PyQt6.QtCore.QDir.setSorting`.

The name filter, file attribute filter, and sorting specification can be overridden using the *nameFilters*, *filters*, and *sort* arguments.

Returns an empty list if the directory is unreadable, does not exist, or if nothing matches the specification.

For large directories this function may cause a memory spike because it creates an instance of a :sip:ref:`~PyQt6.QtCore.QFileInfo` per each entry in the directory. Consider using QDirListing if the goal is to iterate over the items one-by-one.

.. seealso:: :sip:ref:`~PyQt6.QtCore.QDir.entryList`, :sip:ref:`~PyQt6.QtCore.QDir.setNameFilters`, :sip:ref:`~PyQt6.QtCore.QDir.setSorting`, :sip:ref:`~PyQt6.QtCore.QDir.setFilter`, :sip:ref:`~PyQt6.QtCore.QDir.isReadable`, :sip:ref:`~PyQt6.QtCore.QDir.exists`.
