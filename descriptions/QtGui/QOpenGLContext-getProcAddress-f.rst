.. sip:method-description::
    :status: todo
    :pysig: d93d97fc474fffa7f1d18522ac1d0887
    :realsig: (const QByteArray&) const
    :digest: 753f6066a278b323342c6f8dae5c243b

Resolves the function pointer to an OpenGL extension function, identified by *procName*.

Use this function to access OpenGL extension functions or core functions that may not be available as linked symbols on all platforms.

The returned pointer may be platform-dependent. Some systems may return a pointer that is not ``nullptr`` even if the function is not valid or supported.

To reliably check function availability, test for extension support by calling :sip:ref:`~PyQt6.QtGui.QOpenGLContext.hasExtension`. For core functions, check the current context's version via :sip:ref:`~PyQt6.QtGui.QSurfaceFormat.version` in the :sip:ref:`~PyQt6.QtGui.QSurfaceFormat` returned by :sip:ref:`~PyQt6.QtGui.QOpenGLContext.format`.
