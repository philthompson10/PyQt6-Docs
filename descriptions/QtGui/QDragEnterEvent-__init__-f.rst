.. sip:method-description::
    :status: todo
    :pysig: d56187e8b4f5a880787f37be6320f776
    :realsig: (QPointF, Qt::DropActions, const QMimeData*, Qt::MouseButtons, Qt::KeyboardModifiers)
    :digest: 7ff73229b27413e6d858cce38e0813dd

Constructs a :sip:ref:`~PyQt6.QtGui.QDragEnterEvent` that represents a drag entering a widget at the given *point* with mouse and keyboard states specified by *buttons* and *modifiers*.

The drag data is passed as MIME-encoded information in *data*, and the specified *actions* describe the possible types of drag and drop operation that can be performed.

**Warning:** Do not create a :sip:ref:`~PyQt6.QtGui.QDragEnterEvent` yourself since these objects rely on Qt's internal state.
