.. sip:enum-member-description::
    :status: todo
    :value: 28
    :digest: 10021884016b91af9899d3a27e98a00d

Indicates that :sip:ref:`~PyQt6.QtGui.QRhiRenderBuffer.createFrom` is supported. For most graphics APIs this is not sensible because :sip:ref:`~PyQt6.QtGui.QRhiRenderBuffer` encapsulates texture objects internally, just like :sip:ref:`~PyQt6.QtGui.QRhiTexture`. With OpenGL however, renderbuffer object exist as a separate object type in the API, and in certain environments (for example, where one may want to associated a renderbuffer object with an EGLImage object) it is important to allow wrapping an existing OpenGL renderbuffer object with a :sip:ref:`~PyQt6.QtGui.QRhiRenderBuffer`.
