.. sip:method-description::
    :status: todo
    :pysig: 822aca0599717d872944a531af85d744
    :realsig: (int, QSize, QPdfDocumentRenderOptions, QImage::Format, QColor)
    :digest: 03d94941743479697472e29057b904cc

Renders the *page* into a :sip:ref:`~PyQt6.QtGui.QImage` of size *imageSize* with the given *format* according to the provided *renderOptions*.

The *format* is :sip:ref:`~PyQt6.QtGui.QImage.Format.Format_ARGB32` by default. Before rendering, the image is filled with the given *fillColor*, which is :sip:ref:`~PyQt6.QtCore.Qt.GlobalColor.transparent` by default. Thus the default result is suitable for compositing onto any background; but you can specify a different background color to get an image suitable for direct rendering. Some PDF pages may include their own background: if the rendering is fully opaque, it will cover up the background color.

Returns the rendered page or an empty image in case of an error.

**Note:** If the *imageSize* does not match the aspect ratio of the page in the PDF document, the page is rendered scaled, so that it covers the complete *imageSize*.

**Note:** The *format* and *fillColor* arguments were added in 6.12.
