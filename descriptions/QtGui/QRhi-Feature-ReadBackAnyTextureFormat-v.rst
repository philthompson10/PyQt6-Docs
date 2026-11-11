.. sip:enum-member-description::
    :status: todo
    :value: 25
    :digest: ab8b8e8662304e5641797503263c89f9

Indicates that reading back texture contents can be expected to work for any :sip:ref:`~PyQt6.QtGui.QRhiTexture.Format`. Backends other than OpenGL can be expected to return true for this feature. When reported as false, which will typically happen with OpenGL, only the formats :sip:ref:`~PyQt6.QtGui.QRhiTexture.Format.RGBA8` and :sip:ref:`~PyQt6.QtGui.QRhiTexture.Format.BGRA8` are guaranteed to be supported for readbacks. In addition, with OpenGL, but not OpenGL ES, reading back the 1 byte per component formats :sip:ref:`~PyQt6.QtGui.QRhiTexture.Format.R8` and :sip:ref:`~PyQt6.QtGui.QRhiTexture.Format.RED_OR_ALPHA8` are supported as well. Reading back floating point formats :sip:ref:`~PyQt6.QtGui.QRhiTexture.Format.RGBA16F` and RGBA32F may work too with OpenGL, as long as the implementation provides support for these, but :sip:ref:`~PyQt6.QtGui.QRhi` can give no guarantees, as indicated by this flag.
