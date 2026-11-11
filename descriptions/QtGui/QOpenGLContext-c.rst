.. sip:class-description::
    :status: todo
    :brief: Represents a native OpenGL context, enabling OpenGL rendering on a QSurface
    :digest: 1c9718419527d63e4e884b50f68fdcfe

The :sip:ref:`~PyQt6.QtGui.QOpenGLContext` class represents a native OpenGL context, enabling OpenGL rendering on a :sip:ref:`~PyQt6.QtGui.QSurface`.

:sip:ref:`~PyQt6.QtGui.QOpenGLContext` represents the OpenGL state of an underlying OpenGL context. To set up a context, set its screen and format such that they match those of the surface or surfaces with which the context is meant to be used, if necessary make it share resources with other contexts with :sip:ref:`~PyQt6.QtGui.QOpenGLContext.setShareContext`, and finally call :sip:ref:`~PyQt6.QtGui.QOpenGLContext.create`. Use the return value or :sip:ref:`~PyQt6.QtGui.QOpenGLContext.isValid` to check if the context was successfully initialized.

A context can be made current against a given surface by calling :sip:ref:`~PyQt6.QtGui.QOpenGLContext.makeCurrent`. When OpenGL rendering is done, call :sip:ref:`~PyQt6.QtGui.QOpenGLContext.swapBuffers` to swap the front and back buffers of the surface, so that the newly rendered content becomes visible. To be able to support certain platforms, :sip:ref:`~PyQt6.QtGui.QOpenGLContext` requires that you call :sip:ref:`~PyQt6.QtGui.QOpenGLContext.makeCurrent` again before starting rendering a new frame, after calling :sip:ref:`~PyQt6.QtGui.QOpenGLContext.swapBuffers`.

If the context is temporarily not needed, such as when the application is not rendering, it can be useful to delete it in order to free resources. You can connect to the :sip:ref:`~PyQt6.QtGui.QOpenGLContext.aboutToBeDestroyed` signal to clean up any resources that have been allocated with different ownership from the :sip:ref:`~PyQt6.QtGui.QOpenGLContext` itself.

Once a :sip:ref:`~PyQt6.QtGui.QOpenGLContext` has been made current, you can render to it in a platform independent way by using Qt's OpenGL enablers such as QOpenGLFunctions, :sip:ref:`~PyQt6.QtOpenGL.QOpenGLBuffer`, :sip:ref:`~PyQt6.QtOpenGL.QOpenGLShaderProgram`, and :sip:ref:`~PyQt6.QtOpenGL.QOpenGLFramebufferObject`. It is also possible to use the platform's OpenGL API directly, without using the Qt enablers, although potentially at the cost of portability. The latter is necessary when wanting to use OpenGL 1.x or OpenGL ES 1.x.

For more information about the OpenGL API, refer to the official `OpenGL documentation <http://www.opengl.org>`_.

For an example of how to use :sip:ref:`~PyQt6.QtGui.QOpenGLContext` see the `OpenGL Window <https://doc.qt.io/qt-6/qtopengl-openglwindow-example.html>`_ example.

.. _qopenglcontext-thread-affinity:

Thread Affinity
---------------

:sip:ref:`~PyQt6.QtGui.QOpenGLContext` can be moved to a different thread with moveToThread(). Do not call :sip:ref:`~PyQt6.QtGui.QOpenGLContext.makeCurrent` from a different thread than the one to which the :sip:ref:`~PyQt6.QtGui.QOpenGLContext` object belongs. A context can only be current in one thread and against one surface at a time, and a thread only has one context current at a time.

.. _qopenglcontext-context-resource-sharing:

Context Resource Sharing
------------------------

Resources such as textures and vertex buffer objects can be shared between contexts. Use :sip:ref:`~PyQt6.QtGui.QOpenGLContext.setShareContext` before calling :sip:ref:`~PyQt6.QtGui.QOpenGLContext.create` to specify that the contexts should share these resources. :sip:ref:`~PyQt6.QtGui.QOpenGLContext` internally keeps track of a :sip:ref:`~PyQt6.QtGui.QOpenGLContextGroup` object which can be accessed with :sip:ref:`~PyQt6.QtGui.QOpenGLContext.shareGroup`, and which can be used to find all the contexts in a given share group. A share group consists of all contexts that have been successfully initialized and are sharing with an existing context in the share group. A non-sharing context has a share group consisting of a single context.

.. _qopenglcontext-default-framebuffer:

Default Framebuffer
-------------------

On certain platforms, a framebuffer other than 0 might be the default frame buffer depending on the current surface. Instead of calling glBindFramebuffer(0), it is recommended that you use glBindFramebuffer(ctx->\ :sip:ref:`~PyQt6.QtGui.QOpenGLContext.defaultFramebufferObject`), to ensure that your application is portable between different platforms. However, if you use QOpenGLFunctions::glBindFramebuffer(), this is done automatically for you.

**Warning:** WebAssembly

We recommend that only one :sip:ref:`~PyQt6.QtGui.QOpenGLContext` is made current with a :sip:ref:`~PyQt6.QtGui.QSurface`, for the entire lifetime of the :sip:ref:`~PyQt6.QtGui.QSurface`. Should more than once context be used, it is important to understand that multiple :sip:ref:`~PyQt6.QtGui.QOpenGLContext` instances may be backed by the same native context underneath with the WebAssembly platform. Therefore, calling :sip:ref:`~PyQt6.QtGui.QOpenGLContext.makeCurrent` with the same :sip:ref:`~PyQt6.QtGui.QSurface` on two :sip:ref:`~PyQt6.QtGui.QOpenGLContext` objects may not switch to a different native context in the second call. As a result, any OpenGL state changes done after the second :sip:ref:`~PyQt6.QtGui.QOpenGLContext.makeCurrent` may alter the state of the first :sip:ref:`~PyQt6.QtGui.QOpenGLContext` as well, as they are all backed by the same native context.

**Note:** This means that when targeting WebAssembly with existing OpenGL-based Qt code, some porting may be required to cater to these limitations.

.. _qopenglcontext-security-considerations:

Security Considerations
-----------------------

All data consumed by :sip:ref:`~PyQt6.QtGui.QOpenGLContext` and the classes building on it, such as QOpenGLFunctions, the :sip:ref:`~PyQt6.QtOpenGL` module classes, and :sip:ref:`~PyQt6.QtGui.QRhi` with its OpenGL backend, is expected to be trusted content. This includes shader source code, vertex and index data, textures and other pixel data, and all parameters passed to OpenGL functions. Qt does not validate or sanitize any of it.

Note also that :sip:ref:`~PyQt6.QtGui.QOpenGLContext.getProcAddress` returns a raw function pointer resolved by name from the OpenGL implementation. Qt cannot check that the signature the caller casts it to matches the one the implementation provides; getting this wrong results in undefined behavior.

The OpenGL implementation, meaning the driver and, on platforms that have one, the library that dispatches to it, is a trusted, in-process platform dependency. Qt loads it and calls into it directly, without any sandboxing or verification, in the same way as it treats the Vulkan implementation.

Which library is loaded is decided by the platform's ordinary shared library search order and, on some platforms, by environment variables. That selection is part of the deployment's trusted configuration: a deployment that does not control it does not control which native code runs inside the process.

**Warning:** Application developers are advised to carefully consider the potential implications before allowing the feeding of user-provided content that is not part of the application and is not under the developers' control.

.. seealso:: QOpenGLFunctions, :sip:ref:`~PyQt6.QtOpenGL.QOpenGLBuffer`, :sip:ref:`~PyQt6.QtOpenGL.QOpenGLShaderProgram`, :sip:ref:`~PyQt6.QtOpenGL.QOpenGLFramebufferObject`.
