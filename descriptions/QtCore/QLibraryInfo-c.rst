.. sip:class-description::
    :status: todo
    :brief: Information about the Qt libraries
    :digest: dd1b710530b68e22a1c0e10320c749a1

The :sip:ref:`~PyQt6.QtCore.QLibraryInfo` class provides information about the Qt libraries.

This class provides an abstraction for accessing information about the Qt libraries which the application is using, such as run-time paths, or the build configuration of the Qt libraries.

The default run-time paths depend on the Qt build configuration, as well as whether the Qt libraries have been relocated, and possibly bundled along with the application.

You can use a ``qt.conf`` file to override the default paths, in case your deployment situation does not match the defaults. For more information, see the Using qt.conf documentation.

.. seealso:: :sip:ref:`~PyQt6.QtCore.QSysInfo`.
