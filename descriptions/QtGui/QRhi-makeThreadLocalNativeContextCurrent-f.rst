.. sip:method-description::
    :status: todo
    :pysig: c506ff134babdd6e68ab3e6350e95305
    :realsig: ()
    :digest: c45c8a9e178c67af701313822ef58718

With OpenGL this makes the OpenGL context current on the current thread. The function has no effect with other backends.

Calling this function is relevant typically in Qt framework code, when one has to ensure external OpenGL code provided by the application can still run like it did before with direct usage of OpenGL, as long as the :sip:ref:`~PyQt6.QtGui.QRhi` is using the OpenGL backend.

Returns false when failed, similarly to :sip:ref:`~PyQt6.QtGui.QOpenGLContext.makeCurrent`. When the operation failed, :sip:ref:`~PyQt6.QtGui.QRhi.isDeviceLost` can be called to determine if there was a loss of context situation. Such a check is equivalent to checking via :sip:ref:`~PyQt6.QtGui.QOpenGLContext.isValid`.

.. seealso:: :sip:ref:`~PyQt6.QtGui.QOpenGLContext.makeCurrent`, :sip:ref:`~PyQt6.QtGui.QOpenGLContext.isValid`.
