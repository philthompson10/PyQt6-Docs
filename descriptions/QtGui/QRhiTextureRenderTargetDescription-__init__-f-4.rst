.. sip:method-description::
    :status: todo
    :pysig: 182054a24a261966a33835ee0bdd2d5c
    :realsig: (const QRhiColorAttachment&, QRhiTexture*)
    :digest: fd3c955312fd3dc75fb6129e0fbad7d2

Constructs a texture render target description with two attachments, a color attachment described by *colorAttachment*, and a depth attachment with *depthTexture*.

**Note:** *depthTexture* must have a suitable format, such as :sip:ref:`~PyQt6.QtGui.QRhiTexture.Format.D16` or :sip:ref:`~PyQt6.QtGui.QRhiTexture.Format.D32F`.
