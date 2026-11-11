.. sip:method-description::
    :status: todo
    :pysig: eaac8f7e6bc8e218b9735549cf37a09d
    :realsig: (const QCanvasPath&, int)
    :digest: 32c79cb0a80e37dc37b7be94eed44824

Fills the *path* with the current fill style and fill rule, and belonging into *pathGroup*. Painting through :sip:ref:`~PyQt6.QtCanvasPainter.QCanvasPath` is optimal when the path contains more commands and is mostly static.

When *pathGroup* is ``-1``, the path will not be cached on the GPU side. This is the default. To request caching of path data, pass a value equal to or greater than ``0``. More information about using path cache groups can be found in the :sip:ref:`~PyQt6.QtCanvasPainter.QCanvasPath` documentation.

Calling :sip:ref:`~PyQt6.QtCanvasPainter.QCanvasPainter.beginPath` before this method is not required.

+------------------------------+------------------------------------------+
| |image-qcpainter-fill2-webp| | ::                                       |
|                              |                                          |
|                              |     // m_path is QCanvasPath             |
|                              |     if (m_path.isEmpty()) {              |
|                              |         for (int i = 0; i < 16; i++) {   |
|                              |             qreal w = 100 + 60 * sin(i); |
|                              |             m_path.rect(100 - w * 0.5,   |
|                              |                         22 + i * 10,     |
|                              |                         w, 6);           |
|                              |         }                                |
|                              |     }                                    |
|                              |     p->fill(m_path);                     |
+------------------------------+------------------------------------------+

.. seealso:: :sip:ref:`~PyQt6.QtCanvasPainter.QCanvasPainter.setFillStyle`, :sip:ref:`~PyQt6.QtCanvasPainter.QCanvasPainter.setFillRule`, :sip:ref:`~PyQt6.QtCanvasPainter.QCanvasPainter.removePathGroup`.

.. |image-qcpainter-fill2-webp| image:: ../../../images/qcpainter-fill2.webp
