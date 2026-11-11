.. sip:method-description::
    :status: todo
    :pysig: 13589a9b9c4c6c30ca426ce536937662
    :realsig: (const QRectF&)
    :digest: 32e8423dcca49e9411e24466b5bc5e06

Creates a new ellipse shaped sub-path into *rect*. This ellipse will cover the *rect* area.

+---------------------------------+------------------------------------+
| |image-qcpainter-ellipse2-webp| | ::                                 |
|                                 |                                    |
|                                 |     QRectF rect(40, 20, 120, 160); |
|                                 |     p->fillRect(rect);             |
|                                 |     p->beginPath();                |
|                                 |     p->ellipse(rect);              |
|                                 |     p->stroke();                   |
+---------------------------------+------------------------------------+

.. |image-qcpainter-ellipse2-webp| image:: ../../../images/qcpainter-ellipse2.webp
