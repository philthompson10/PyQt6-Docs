.. sip:method-description::
    :status: todo
    :pysig: fa7153f7ed1cb6c0fcf2ffb2fac21748
    :realsig: (int)
    :digest: 705c0b529f11e28b446568e617afd185

This is an image format specific function that set the compression of an image. For image formats that do not support setting the compression, this value is ignored.

The value range of *compression* depends on the image format:

+--------------+----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
| Image Format | Supported Values                                                                                                                                                                                                                 |
+==============+==================================================================================================================================================================================================================================+
| PNG          | Values in the range from 0 (no compression) to 100 (low visual quality, maximum compression). This value is the inverse to *quality* in :sip:ref:`~PyQt6.QtGui.QImageWriter.setQuality`. The two options are mutually exclusive. |
+--------------+----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
| TGA          | 0 - No compression  1 - RLE compression                                                                                                                                                                                          |
+--------------+----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
| TIFF         | 0 - No compression  1 - LZW compression  2 - RLE compression  3 - CCITT Group 3 fax encoding  4 - CCITT Group 4 fax encoding  5 - JPEG compression                                                                               |
+--------------+----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+

.. seealso:: :sip:ref:`~PyQt6.QtGui.QImageWriter.compression`, :sip:ref:`~PyQt6.QtGui.QImageWriter.setQuality`.
