.. sip:method-description::
    :status: todo
    :pysig: fb51eb2740812f4466a824231ed4bce3
    :realsig: (const QImage&)
    :digest: befce7614e185afb1cfd64f8db5c7457

Constructs a mip level description with a *image*.

The :sip:ref:`~PyQt6.QtGui.QImage.size` of *image* must match the size of the mip level. For level 0 that is the texture size.

The bit depth of *image* must be compatible with the :sip:ref:`~PyQt6.QtGui.QRhiTexture.Format`.

To describe a partial upload, call setSourceSize(), setSourceTopLeft(), or setDestinationTopLeft() afterwards.
