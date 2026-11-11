.. sip:method-description::
    :status: todo
    :pysig: 5237000fc3bc4f513a579caca380c129
    :realsig: (QColor)
    :digest: d719667e158d96dfc297be8fb64aab8b

Sets the fill style to a solid *color*. The default fill style is solid black (0, 0, 0, 1).

+----------------------------------+----------------------------------------------+
| |image-qcpainter-fillstyle-webp| | ::                                           |
|                                  |                                              |
|                                  |     p->setFillStyle(QColorConstants::Black); |
|                                  |     p->fillRect(20, 20, 160, 160);           |
|                                  |     p->setFillStyle(QColor(0, 65, 74));      |
|                                  |     p->fillRect(40, 40, 120, 120);           |
|                                  |     p->setFillStyle("#2CDE85");              |
|                                  |     p->fillRect(60, 60, 80, 80);             |
+----------------------------------+----------------------------------------------+

.. |image-qcpainter-fillstyle-webp| image:: ../../../images/qcpainter-fillstyle.webp
