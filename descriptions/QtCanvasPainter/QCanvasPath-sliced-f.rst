.. sip:method-description::
    :status: todo
    :pysig: 31d0ced984ff97ac32beb5740653d359
    :realsig: (qsizetype, qsizetype, const QTransform&) const
    :digest: 41dd7e213f78d35bb7288d86c5aba48e

Returns a new path containing the commands from this path, starting from the command at *start* and including *count* amount of commands, optionally using *transform* to alter the path points.

The range of *start* and *count* is checked, so that commands are not accessed more than :sip:ref:`~PyQt6.QtCanvasPainter.QCanvasPath.commandsSize`. In case the command at *start* is not ``MoveTo``, the first command will be replaced with ``MoveTo`` so that this slice is an individual path.
