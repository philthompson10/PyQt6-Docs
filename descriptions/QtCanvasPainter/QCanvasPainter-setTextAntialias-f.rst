.. sip:method-description::
    :status: todo
    :pysig: 546ade640b6edfbc8a086ef31347e768
    :realsig: (qreal)
    :digest: 41de7f5fca5a658ca268c0712ffc9ff8

Sets the current text antialiasing amount. The value *antialias* is a multiplier to normal antialiasing, meaning that ``0.0`` disables antialiasing and 2.0 doubles it. The default value is 1.0.

**Note:** Due to the text antialiasing technique used (SDF), the maximum antialiasing amount is quite limited and this affects less when the font size is small.

+--------------------------------------+-------------------------------------------------+
| |image-qcpainter-textantialias-webp| | ::                                              |
|                                      |                                                 |
|                                      |     QFont font("Titillium Web", 20);            |
|                                      |     p->setFont(font);                           |
|                                      |     p->setTextAntialias(1.0);                   |
|                                      |     p->fillText("Antialiasing: 1.0", 100, 25);  |
|                                      |     p->setTextAntialias(2.0);                   |
|                                      |     p->fillText("Antialiasing: 2.0", 100, 75);  |
|                                      |     p->setTextAntialias(3.0);                   |
|                                      |     p->fillText("Antialiasing: 3.0", 100, 125); |
|                                      |     p->setTextAntialias(4.0);                   |
|                                      |     p->fillText("Antialiasing: 4.0", 100, 175); |
+--------------------------------------+-------------------------------------------------+

.. |image-qcpainter-textantialias-webp| image:: ../../../images/qcpainter-textantialias.webp
