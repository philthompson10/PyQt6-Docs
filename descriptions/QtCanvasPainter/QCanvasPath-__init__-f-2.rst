.. sip:method-description::
    :status: todo
    :pysig: acde3b00e3ffe3a88bf8aad5b154f0cf
    :realsig: (qsizetype, qsizetype)
    :digest: 7617f574c8f1dd5f8f52742299aa0951

Constructs an empty path, allocating space for *commandsSize* amount of commands and optionally *commandsDataSize* amount of data. If *commandsDataSize* parameter is not given, space is automatically reserved for ``2 \* commandsSize`` amount of data, which is optimal amount when the path commands are straight lines (\ :sip:ref:`~PyQt6.QtCanvasPainter.QCanvasPath.moveTo`, :sip:ref:`~PyQt6.QtCanvasPainter.QCanvasPath.lineTo`, :sip:ref:`~PyQt6.QtCanvasPainter.QCanvasPath.rect`).

Reserving correct space is an optimization for path creation and memory usage. It isn't mandatory as sufficient space will automatically be ensured while adding commands to the path.

.. seealso:: :sip:ref:`~PyQt6.QtCanvasPainter.QCanvasPath.reserve`.
