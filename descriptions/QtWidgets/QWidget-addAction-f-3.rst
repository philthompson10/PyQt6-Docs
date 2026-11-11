.. sip:method-description::
    :status: todo
    :pysig: ea9c9401f9c67764cb880c6fb28ff2d6
    :realsig: (const QString&, const QKeySequence&)
    :digest: 598eb2c39347185be2a9e88b219c39b4

These convenience functions create a new action with text *text*, icon *icon* and shortcut *shortcut*, if any.

The functions add the newly created action to the widget's list of actions, and return it.

:sip:ref:`~PyQt6.QtWidgets.QWidget` takes ownership of the returned :sip:ref:`~PyQt6.QtGui.QAction`.
