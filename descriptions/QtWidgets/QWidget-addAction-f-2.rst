.. sip:method-description::
    :status: todo
    :pysig: 9302c3f8ab37885338b396b61353184b
    :realsig: (const QIcon&, const QString&)
    :digest: 598eb2c39347185be2a9e88b219c39b4

These convenience functions create a new action with text *text*, icon *icon* and shortcut *shortcut*, if any.

The functions add the newly created action to the widget's list of actions, and return it.

:sip:ref:`~PyQt6.QtWidgets.QWidget` takes ownership of the returned :sip:ref:`~PyQt6.QtGui.QAction`.
