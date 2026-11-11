.. sip:method-description::
    :status: todo
    :pysig: 6a1bb6ed41f44b60e7bd83b0e9945aa7
    :realsig: (qreal, qreal)
    :digest: 4c202e9c83218c367b40d1140ddbb8d7

Translates the current coordinate system by *x* and *y*.

+----------------------------------+--------------------------------------------+
| |image-qcpainter-translate-webp| | ::                                         |
|                                  |                                            |
|                                  |     auto paintRect = [p]() {               |
|                                  |         p->beginPath();                    |
|                                  |         p->roundRect(20, 20, 160, 60, 10); |
|                                  |         p->fill();                         |
|                                  |         p->stroke();                       |
|                                  |     };                                     |
|                                  |     paintRect();                           |
|                                  |     p->translate(0, 100);                  |
|                                  |     paintRect();                           |
+----------------------------------+--------------------------------------------+

.. |image-qcpainter-translate-webp| image:: ../../../images/qcpainter-translate.webp
