.. sip:method-description::
    :status: todo
    :pysig: e5c8bb2826e45acb2b858f7235b8dea7
    :realsig: (QStringView, const QTransform&)
    :digest: c7bf632cd8fdee186e5218d5d972a7bb

Adds *svgPath* into this path, optionally using *transform* to alter the path points. If the estimated size of the path is known, consider calling :sip:ref:`~PyQt6.QtCanvasPainter.QCanvasPath.reserve` before this.

+---------------------------------+------------------------------------------------------------------+
| |image-qcpainter-addpath3-webp| | ::                                                               |
|                                 |                                                                  |
|                                 |     // m_path is QCanvasPath                                     |
|                                 |     if (m_path.isEmpty()) {                                      |
|                                 |         QString path("M 20 20 C 40 120, 80 120, 100 20 Z");      |
|                                 |         m_path.addPath(path);                                    |
|                                 |         m_path.addPath(path, QTransform::fromTranslate(80, 80)); |
|                                 |     }                                                            |
|                                 |     p->fill(m_path);                                             |
|                                 |     p->stroke(m_path);                                           |
+---------------------------------+------------------------------------------------------------------+

See `W3C SVG Path Data <http://www.w3.org/TR/SVG/paths.html#PathData>`_ for more details on this format.

.. |image-qcpainter-addpath3-webp| image:: ../../../images/qcpainter-addpath3.webp
