.. sip:method-description::
    :status: todo
    :pysig: d41d8cd98f00b204e9800998ecf8427e
    :realsig: ()
    :digest: 876721ad62f0e8cae97308fcec3e6be7

Pushes and saves the current render state into a state stack. A matching :sip:ref:`~PyQt6.QtCanvasPainter.QCanvasPainter.restore` must be used to restore the state.

+-----------------------------+------------------------------------------------+
| |image-qcpainter-save-webp| | ::                                             |
|                             |                                                |
|                             |     p->strokeRect(20, 20, 160, 40);            |
|                             |     // Save and adjust the paint state         |
|                             |     p->save();                                 |
|                             |     p->setStrokeStyle(QColorConstants::Black); |
|                             |     p->setLineWidth(3);                        |
|                             |     p->rotate(0.1);                            |
|                             |     p->strokeRect(20, 80, 180, 20);            |
|                             |     // Restore the saved paint state           |
|                             |     p->restore();                              |
|                             |     p->strokeRect(20, 140, 160, 40);           |
+-----------------------------+------------------------------------------------+

.. seealso:: :sip:ref:`~PyQt6.QtCanvasPainter.QCanvasPainter.restore`.

.. |image-qcpainter-save-webp| image:: ../../../images/qcpainter-save.webp
