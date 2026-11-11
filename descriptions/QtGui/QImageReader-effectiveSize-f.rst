.. sip:method-description::
    :status: todo
    :pysig: 364191bc772363d61cf96ad3eac70cf9
    :realsig: () const
    :digest: 34bd53ff2ed365d1896703cc9da8ff92

Returns the effective size of the image accounting for transformation, without actually reading the image contents.

If the image format does not support this feature, this function returns an invalid size. Qt's built-in image handlers all support this feature, but custom image format plugins are not required to do so.

.. seealso:: :sip:ref:`~PyQt6.QtGui.QImageReader.setAutoTransform`, :sip:ref:`~PyQt6.QtGui.QImageReader.size`, :sip:ref:`~PyQt6.QtGui.QImageIOHandler.ImageOption`, :sip:ref:`~PyQt6.QtGui.QImageIOHandler.option`, :sip:ref:`~PyQt6.QtGui.QImageIOHandler.supportsOption`.
