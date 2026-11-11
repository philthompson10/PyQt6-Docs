.. sip:method-description::
    :status: todo
    :pysig: d52281d1917ca2a53651e9f9039bb038
    :realsig: (QCanvasPainter::CompositeOperation)
    :digest: 53c361e08f44bbfc3f4417fa97347b24

Sets the global composite operation mode to *operation*. This mode is applied to all painting operations. The default mode is ``QCanvasPainter::CompositeOperation::SourceOver``.

**Note:** To work properly, composite modes require enabling ``alphaBlending`` and using a transparent background for the canvas.

+----------------------------------------+-----------------------------------------------------------------------------------------+
| |image-qcpainter-globalcomposite-webp| | ::                                                                                      |
|                                        |                                                                                         |
|                                        |     QList<QCanvasPainter::CompositeOperation> modes = {                                 |
|                                        |         QCanvasPainter::CompositeOperation::SourceOver,                                 |
|                                        |         QCanvasPainter::CompositeOperation::SourceAtop,                                 |
|                                        |         QCanvasPainter::CompositeOperation::DestinationOut                              |
|                                        |     };                                                                                  |
|                                        |     for (int i = 0; i < modes.size(); i++) {                                            |
|                                        |         // First item - SourceOver mode                                                 |
|                                        |         p->setGlobalCompositeOperation(QCanvasPainter::CompositeOperation::SourceOver); |
|                                        |         qreal y = 5 + i * 65;                                                           |
|                                        |         p->setFillStyle("#D9F720");                                                     |
|                                        |         p->fillRect(20, y, 140, 40);                                                    |
|                                        |         // Second item - Different modes                                                |
|                                        |         p->setGlobalCompositeOperation(modes[i]);                                       |
|                                        |         p->beginPath();                                                                 |
|                                        |         p->ellipse(130, y + 30, 60, 25);                                                |
|                                        |         p->setStrokeStyle("#00414A");                                                   |
|                                        |         p->setFillStyle("#2CDE85");                                                     |
|                                        |         p->fill();                                                                      |
|                                        |         p->stroke();                                                                    |
|                                        |     }                                                                                   |
+----------------------------------------+-----------------------------------------------------------------------------------------+

.. |image-qcpainter-globalcomposite-webp| image:: ../../../images/qcpainter-globalcomposite.webp
