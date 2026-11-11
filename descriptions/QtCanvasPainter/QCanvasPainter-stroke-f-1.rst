.. sip:method-description::
    :status: todo
    :pysig: eaac8f7e6bc8e218b9735549cf37a09d
    :realsig: (const QCanvasPath&, int)
    :digest: 6949f8976b5e0d42ff7d184f6863633c

Strokes the *path* with the current stroke style and belonging into *pathGroup*. Painting through :sip:ref:`~PyQt6.QtCanvasPainter.QCanvasPath` is optimal when the path contains more commands and is mostly static.

When *pathGroup* is ``-1``, the path's rendering-related data will not be cached. This is the default. To request caching of path data, pass a value equal to or greater than ``0``. More information about using path cache groups can be found in the :sip:ref:`~PyQt6.QtCanvasPainter.QCanvasPath` documentation.

Calling :sip:ref:`~PyQt6.QtCanvasPainter.QCanvasPainter.beginPath` before this method is not required.

+--------------------------------+----------------------------------------+
| |image-qcpainter-stroke2-webp| | ::                                     |
|                                |                                        |
|                                |     // m_path is QCanvasPath           |
|                                |     if (m_path.isEmpty()) {            |
|                                |         for (int i = 0; i < 16; i++) { |
|                                |             int h = 100 + 60 * sin(i); |
|                                |             m_path.rect(22 + i * 10,   |
|                                |                         180 - h,       |
|                                |                         6, h);         |
|                                |         }                              |
|                                |     }                                  |
|                                |     p->stroke(m_path);                 |
+--------------------------------+----------------------------------------+

.. seealso:: :sip:ref:`~PyQt6.QtCanvasPainter.QCanvasPainter.setStrokeStyle`, :sip:ref:`~PyQt6.QtCanvasPainter.QCanvasPainter.removePathGroup`.

.. |image-qcpainter-stroke2-webp| image:: ../../../images/qcpainter-stroke2.webp
