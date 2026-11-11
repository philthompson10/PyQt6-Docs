.. sip:method-description::
    :status: todo
    :pysig: 8886d7464df858628f73f8b61d87845c
    :realsig: (const QCanvasPath&, qsizetype, qsizetype, const QTransform&)
    :digest: e8b9367808cf975423177eb1f3f94bb7

Adds *path* into the current path, starting from the command at *start* and including *count* amount of commands. Optionally using *transform* to alter the path points. The range of *start* and *count* is checked, so that commands are not accessed more than :sip:ref:`~PyQt6.QtCanvasPainter.QCanvasPath.commandsSize`. In case the path shouldn't continue from the current path position, call first :sip:ref:`~PyQt6.QtCanvasPainter.QCanvasPath.moveTo` with ``path.positionAt(start - 1)``.
