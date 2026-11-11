.. sip:method-description::
    :status: todo
    :pysig: 061e21dbb5172691afb79590f5f2a24c
    :realsig: (const QCanvasImage&, int)
    :digest: aaf82464517327ab918219265c651b53

Uses the *image* as the gradient source at the y-coordinate *index*. This is an alternative for setting the gradient stops using e.g. :sip:ref:`~PyQt6.QtCanvasPainter.QCanvasGradient.setStops` or :sip:ref:`~PyQt6.QtCanvasPainter.QCanvasGradient.setColorAt`. The expected default width of the image is 256 pixels, but it can be adjusted by defining the QCPAINTER_GRADIENT_SIZE. Index parameter is optional and not needed when the height of the image is 1 pixel. The maximum value of index should be image height - 1.

Possible reasons to use this method instead of setting stops:

* Slightly faster to create as stops don't need to be parsed. Also, multiple gradients can be included in a single image using *index*.

* The ability to use gradient from design / image directly, instead of converting it to set of stops.

* The ability to have non-linear gradients, like e.g. Gaussian curve.

**Note:** If both the stops and the image have been set, stops will be used.

Here is a simple example of how to use a ``256x1`` gradient image:

+-------------------------------+-------------------------------------------------------+
| |image-gradient1-png|         |                                                       |
+-------------------------------+-------------------------------------------------------+
| |image-qcgradient-image-webp| | ::                                                    |
|                               |                                                       |
|                               |     static QImage image(":/gradient1.png");           |
|                               |     QCanvasImage gradImage = p->addImage(image);      |
|                               |     QRectF rect(0, 0, 200, 200);                      |
|                               |     QCanvasRadialGradient rg(rect.center(), 20, 150); |
|                               |     rg.setImage(gradImage);                           |
|                               |     p->setFillStyle(rg);                              |
|                               |     p->fillRect(rect);                                |
+-------------------------------+-------------------------------------------------------+

.. seealso:: :sip:ref:`~PyQt6.QtCanvasPainter.QCanvasGradient.setStops`.

.. |image-gradient1-png| image:: ../../../images/gradient1.png
.. |image-qcgradient-image-webp| image:: ../../../images/qcgradient-image.webp
