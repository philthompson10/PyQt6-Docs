.. sip:method-description::
    :status: todo
    :pysig: 042905aa76e8d3bc3a57cd84da6a505d
    :realsig: (const QCanvasPath&, const QTransform&)
    :digest: f1c1aad20c050390933c8f722199e10d

Adds *path* into the current path, optionally using *transform* to alter the path points. When *transform* is not provided (or it is identity matrix), this operation is very fast as it reuses the path data.

+--------------------------------+------------------------------------------------------------+
| |image-qcpainter-addpath-webp| | ::                                                         |
|                                |                                                            |
|                                |     // m_path is QCanvasPath                               |
|                                |     if (m_path.isEmpty())                                  |
|                                |         m_path.circle(60, 60, 40);                         |
|                                |     p->beginPath();                                        |
|                                |     p->addPath(m_path);                                    |
|                                |     p->addPath(m_path, QTransform::fromTranslate(80, 80)); |
|                                |     p->fill();                                             |
|                                |     p->stroke();                                           |
+--------------------------------+------------------------------------------------------------+

.. |image-qcpainter-addpath-webp| image:: ../../../images/qcpainter-addpath.webp
