.. sip:method-description::
    :status: todo
    :pysig: c506ff134babdd6e68ab3e6350e95305
    :realsig: (bool)
    :digest: d591451f64fba265d60feb58b17dcb02

Sets the winding enforcing to *enabled*. Setting this to ``false`` disables enforcing of path winding to match what has been set into :sip:ref:`~PyQt6.QtCanvasPainter.QCanvasPainter.setPathWinding`. Disabling allows e.g. creating holes into paths by adding the points in clock wise order. Disabling can also increase the performance. The default value is ``true``.

+-------------------------------------+--------------------------------------+
| |image-qcpainter-pathwinding2-webp| | ::                                   |
|                                     |                                      |
|                                     |     p->setWindingEnforce(false);     |
|                                     |     p->beginPath();                  |
|                                     |     // Outer shape, counterclockwise |
|                                     |     p->moveTo(20, 20);               |
|                                     |     p->lineTo(100, 180);             |
|                                     |     p->lineTo(180, 20);              |
|                                     |     p->closePath();                  |
|                                     |     // Inner shape, clockwise        |
|                                     |     p->moveTo(100, 40);              |
|                                     |     p->lineTo(125, 90);              |
|                                     |     p->lineTo(75, 90);               |
|                                     |     p->closePath();                  |
|                                     |     p->fill();                       |
|                                     |     p->stroke();                     |
+-------------------------------------+--------------------------------------+

.. |image-qcpainter-pathwinding2-webp| image:: ../../../images/qcpainter-pathwinding2.webp
