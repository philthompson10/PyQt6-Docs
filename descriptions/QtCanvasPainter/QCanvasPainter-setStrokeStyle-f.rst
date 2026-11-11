.. sip:method-description::
    :status: todo
    :pysig: 5237000fc3bc4f513a579caca380c129
    :realsig: (QColor)
    :digest: 0566577362380d20bfb6d381f7d4c384

Sets the stroke style to a solid *color*. The default stroke style is solid black color (0, 0, 0, 1).

+------------------------------------+------------------------------------------------+
| |image-qcpainter-strokestyle-webp| | ::                                             |
|                                    |                                                |
|                                    |     p->setStrokeStyle(QColorConstants::Black); |
|                                    |     p->strokeRect(20, 20, 160, 160);           |
|                                    |     p->setStrokeStyle(QColor(0, 65, 74));      |
|                                    |     p->strokeRect(40, 40, 120, 120);           |
|                                    |     p->setStrokeStyle("#2CDE85");              |
|                                    |     p->strokeRect(60, 60, 80, 80);             |
+------------------------------------+------------------------------------------------+

.. |image-qcpainter-strokestyle-webp| image:: ../../../images/qcpainter-strokestyle.webp
