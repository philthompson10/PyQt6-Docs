.. sip:method-description::
    :status: todo
    :pysig: 252f2463b17d7b65060495677c920d4c
    :realsig: (const QStringList&)
    :digest: 638e830c1c160d18e71d257dda3b56a3

Sets the list of directories where the engine searches for native plugins for imported modules (referenced in the ``qmldir`` file) to *paths*. Qt assumes that all files and folders under *paths* come from a trusted source.

By default, the list contains only ``.``, i.e. the engine searches in the directory of the ``qmldir`` file itself.

.. seealso:: :sip:ref:`~PyQt6.QtQml.QQmlEngine.pluginPathList`, :sip:ref:`~PyQt6.QtQml.QQmlEngine.addPluginPath`.
