.. sip:method-description::
    :status: todo
    :pysig: acde3b00e3ffe3a88bf8aad5b154f0cf
    :realsig: (qsizetype, qsizetype)
    :digest: e666a4fcbf0f12bd9130ec7a57473ecb

Reserves a given amounts of space in :sip:ref:`~PyQt6.QtCanvasPainter.QCanvasPath`'s internal memory.

Attempts to allocate memory for at least *commandsSize* commands and *commandsDataSize* data points. Some path elements require multiple commands, see :sip:ref:`~PyQt6.QtCanvasPainter.QCanvasPath.commandsSize` and :sip:ref:`~PyQt6.QtCanvasPainter.QCanvasPath.commandsDataSize`.

If *commandsDataSize* is not specified, then space is automatically reserved for ``2 \* commandsSize`` amount of data, which is the optimal amount when the path commands are straight lines (\ :sip:ref:`~PyQt6.QtCanvasPainter.QCanvasPath.moveTo`, :sip:ref:`~PyQt6.QtCanvasPainter.QCanvasPath.lineTo`, :sip:ref:`~PyQt6.QtCanvasPainter.QCanvasPath.rect`).

Reserving correct space is an optimization for path creation and memory usage. It isn't mandatory as sufficient space will automatically be ensured while adding commands into the path.

.. seealso:: :sip:ref:`~PyQt6.QtCanvasPainter.QCanvasPath.squeeze`, :sip:ref:`~PyQt6.QtCanvasPainter.QCanvasPath.commandsCapacity`, :sip:ref:`~PyQt6.QtCanvasPainter.QCanvasPath.commandsDataCapacity`.
