.. sip:enum-member-description::
    :status: todo
    :value: 3
    :digest: f2f836798e91eb7c9679d4c2b6aba603

The maximum number of color attachments for a :sip:ref:`~PyQt6.QtGui.QRhiTextureRenderTarget`, in case multiple render targets are supported. When MRT is not supported, the value is 1. Otherwise this is typically 8, but watch out for the fact that OpenGL only mandates 4 as the minimum, and that is what some OpenGL ES implementations provide.
