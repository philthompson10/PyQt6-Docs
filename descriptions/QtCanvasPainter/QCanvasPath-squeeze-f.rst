.. sip:method-description::
    :status: todo
    :pysig: d41d8cd98f00b204e9800998ecf8427e
    :realsig: ()
    :digest: 7667671f6590f4a83ba8237b6b6e4b21

Releases any memory not required to store the path commands and data. This can be used to reduce the memory usage after calling the :sip:ref:`~PyQt6.QtCanvasPainter.QCanvasPath.reserve`.

Normally this is not needed to be used, but it can be useful when the path size has been big due to reserving or adding many elements (\ :sip:ref:`~PyQt6.QtCanvasPainter.QCanvasPath.lineTo`, :sip:ref:`~PyQt6.QtCanvasPainter.QCanvasPath.bezierCurveTo` etc.) and then size is expected to be much smaller in future so calling first ``reserve()`` and then ``squeeze()``, will release some memory.

.. seealso:: :sip:ref:`~PyQt6.QtCanvasPainter.QCanvasPath.reserve`.
