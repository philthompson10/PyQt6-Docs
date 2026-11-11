.. sip:method-description::
    :status: todo
    :pysig: 8886d7464df858628f73f8b61d87845c
    :realsig: (const QCanvasPath&, qsizetype, qsizetype, const QTransform&)
    :digest: 1ed41f2bcbf2c2e1b3f62f1e32ef010e

Adds *path* into the current path, starting from the command at *start* and including *count* amount of commands. Optionally using *transform* to alter the path points. The range of *start* and *count* is checked, so that commands are not accessed more than :sip:ref:`~PyQt6.QtCanvasPainter.QCanvasPath.commandsSize`. In case the path shouldn't continue from the current path position, call first :sip:ref:`~PyQt6.QtCanvasPainter.QCanvasPainter.moveTo` e.g. with ``path.positionAt(start - 1)``.

+---------------------------------+----------------------------------------------------+
| |image-qcpainter-addpath2-webp| | ::                                                 |
|                                 |                                                    |
|                                 |     // m_path is QCanvasPath                       |
|                                 |     if (m_path.isEmpty()) {                        |
|                                 |         m_path.moveTo(20, 60);                     |
|                                 |         for (int i = 1; i < 160; i++) {            |
|                                 |             m_path.lineTo(20 + i,                  |
|                                 |                           60 + 20 * sin(0.1 * i)); |
|                                 |         }                                          |
|                                 |     }                                              |
|                                 |     p->stroke(m_path);                             |
|                                 |     p->beginPath();                                |
|                                 |     p->addPath(m_path, 20, 100,                    |
|                                 |                QTransform::fromTranslate(0, 80));  |
|                                 |     p->stroke();                                   |
+---------------------------------+----------------------------------------------------+

.. |image-qcpainter-addpath2-webp| image:: ../../../images/qcpainter-addpath2.webp
