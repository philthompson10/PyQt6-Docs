.. sip:method-description::
    :status: todo
    :pysig: c506ff134babdd6e68ab3e6350e95305
    :realsig: () const
    :digest: 754d2f1337bbc2fc419e5f3b9231b84c

Returns ``true`` if the underlying graphics API uses depth range [0, 1] in clip space.

In practice this is ``false`` for OpenGL only, because OpenGL uses a post-projection depth range of [-1, 1]. (not to be confused with the NDC-to-window mapping controlled by glDepthRange(), which uses a range of [0, 1], unless overridden by the :sip:ref:`~PyQt6.QtGui.QRhiViewport`) In some OpenGL versions glClipControl() could be used to change this, but the OpenGL backend of :sip:ref:`~PyQt6.QtGui.QRhi` does not use that function as it is not available in OpenGL ES or OpenGL versions lower than 4.5.

**Note:** :sip:ref:`~PyQt6.QtGui.QRhi.clipSpaceCorrMatrix` includes the corresponding adjustment in its returned matrix. Therefore, many users of :sip:ref:`~PyQt6.QtGui.QRhi` do not need to take any further measures apart from pre-multiplying their projection matrices with :sip:ref:`~PyQt6.QtGui.QRhi.clipSpaceCorrMatrix`. However, some graphics techniques, such as, some types of shadow mapping, involve working with and outputting depth values in the shaders. These will need to query and take the value of this function into account as appropriate.
