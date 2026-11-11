.. sip:method-description::
    :status: todo
    :pysig: 464116456943d857ef223b2d24ec328b
    :realsig: (const QString&)
    :digest: 31a4c6dc0152c8205577dcb44d9314f1

Adds *path* as a directory where the engine searches for native plugins for imported modules (referenced in the ``qmldir`` file). Qt assumes that all files and folders under *path* come from a trusted source.

By default, the list contains only ``.``, i.e. the engine searches in the directory of the ``qmldir`` file itself.

The newly added *path* will be first in the :sip:ref:`~PyQt6.QtQml.QQmlEngine.pluginPathList`.

.. seealso:: :sip:ref:`~PyQt6.QtQml.QQmlEngine.setPluginPathList`.
