.. sip:class-description::
    :status: todo
    :brief: Encapsulates an OpenGL texture object
    :digest: 5ec0c0571871db2104cb84cb1f06b74c

The :sip:ref:`~PyQt6.QtOpenGL.QOpenGLTexture` class encapsulates an OpenGL texture object.

:sip:ref:`~PyQt6.QtOpenGL.QOpenGLTexture` makes it easy to work with OpenGL textures and the myriad features and targets that they offer depending upon the capabilities of your OpenGL implementation.

The typical usage pattern for :sip:ref:`~PyQt6.QtOpenGL.QOpenGLTexture` is

* Instantiate the object specifying the texture target type

* Set properties that affect the storage requirements e.g. storage format, dimensions

* Allocate the server-side storage

* Optionally upload pixel data

* Optionally set any additional properties e.g. filtering and border options

* Render with texture or render to texture

In the common case of simply using a :sip:ref:`~PyQt6.QtGui.QImage` as the source of texture pixel data most of the above steps are performed automatically.

::

    // Prepare texture
    QOpenGLTexture *texture = new QOpenGLTexture(QImage(fileName).flipped());
    texture->setMinificationFilter(QOpenGLTexture::LinearMipMapLinear);
    texture->setMagnificationFilter(QOpenGLTexture::Linear);
    ...
    // Render with texture
    texture->bind();
    glDrawArrays(...);

Note that the :sip:ref:`~PyQt6.QtGui.QImage` is flipped vertically to account for the fact that OpenGL and :sip:ref:`~PyQt6.QtGui.QImage` use opposite directions for the y axis. Another option would be to transform your texture coordinates.

**Warning:** All data consumed by :sip:ref:`~PyQt6.QtOpenGL.QOpenGLTexture` is expected to be trusted content. Pixel and image data is passed on to the underlying OpenGL implementation. Application developers are advised to carefully consider the potential implications before passing in user-provided content to functions such as :sip:ref:`~PyQt6.QtOpenGL.QOpenGLTexture.setData`.
