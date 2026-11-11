.. sip:method-description::
    :status: todo
    :pysig: d2ddcdb6e5a00d07eab5a739d1b778e2
    :realsig: (QCanvasPainter::FillRule)
    :digest: e994d84d114890fe581b43edf53d6228

Sets the path fill rule to *fillRule*. This value is applied to all :sip:ref:`~PyQt6.QtCanvasPainter.QCanvasPainter.fill` calls after the rule has been set. The default fill rule is ``QCanvasPainter::FillRule::NonZero``

+---------------------------------+--------------------------------------------------------+
| |image-qcpainter-fillrule-webp| | ::                                                     |
|                                 |                                                        |
|                                 |     auto paintStar = [p]() {                           |
|                                 |         p->beginPath();                                |
|                                 |         p->moveTo(120, 60);                            |
|                                 |         for (int i = 1; i < 6; ++i) {                  |
|                                 |             p->lineTo(60 + 60 * cos(0.8 * i * M_PI),   |
|                                 |                       60 + 60 * sin(0.8 * i * M_PI));  |
|                                 |         }                                              |
|                                 |         p->fill();                                     |
|                                 |         p->stroke();                                   |
|                                 |     };                                                 |
|                                 |     p->setFillRule(QCanvasPainter::FillRule::NonZero); |
|                                 |     paintStar();                                       |
|                                 |     p->translate(75, 75);                              |
|                                 |     p->setFillRule(QCanvasPainter::FillRule::EvenOdd); |
|                                 |     paintStar();                                       |
+---------------------------------+--------------------------------------------------------+

.. |image-qcpainter-fillrule-webp| image:: ../../../images/qcpainter-fillrule.webp
