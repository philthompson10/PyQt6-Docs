.. sip:method-description::
    :status: todo
    :pysig: eed5c663a9110c04fdce085b268c2b9d
    :realsig: (qreal, qreal, qreal)
    :digest: b994705e807baa08bc8f24384c3f20ec

Creates a new circle shaped sub-path centered at ( *centerX*, *centerY*) with *radius*.

+-------------------------------+------------------------------+
| |image-qcpainter-circle-webp| | ::                           |
|                               |                              |
|                               |     p->beginPath();          |
|                               |     p->circle(100, 100, 80); |
|                               |     p->fill();               |
|                               |     p->stroke();             |
+-------------------------------+------------------------------+

.. |image-qcpainter-circle-webp| image:: ../../../images/qcpainter-circle.webp
