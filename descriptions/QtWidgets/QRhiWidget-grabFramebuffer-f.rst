.. sip:method-description::
    :status: todo
    :pysig: fb51eb2740812f4466a824231ed4bce3
    :realsig: () const
    :digest: f7b7b326420399626f4d281baa3eedf9

Renders a new frame, reads the contents of the texture back, and returns it as a :sip:ref:`~PyQt6.QtGui.QImage`.

When an error occurs, a null :sip:ref:`~PyQt6.QtGui.QImage` is returned.

The returned :sip:ref:`~PyQt6.QtGui.QImage` will have a format of :sip:ref:`~PyQt6.QtGui.QImage.Format.Format_RGBA8888`, :sip:ref:`~PyQt6.QtGui.QImage.Format.Format_RGBA16FPx4`, :sip:ref:`~PyQt6.QtGui.QImage.Format.Format_RGBA32FPx4`, or :sip:ref:`~PyQt6.QtGui.QImage.Format.Format_BGR30`, depending on :sip:ref:`~PyQt6.QtWidgets.QRhiWidget.colorBufferFormat`.

:sip:ref:`~PyQt6.QtWidgets.QRhiWidget` does not know the renderer's approach to blending and composition, and therefore cannot know if the output has alpha premultiplied in the RGB color values. Thus ``_Premultiplied`` :sip:ref:`~PyQt6.QtGui.QImage` formats are never used for the returned :sip:ref:`~PyQt6.QtGui.QImage`, even when it would be appropriate. It is up to the caller to reinterpret the resulting data as it sees fit.

**Note:** This function can also be called when the :sip:ref:`~PyQt6.QtWidgets.QRhiWidget` is not added to a widget hierarchy belonging to an on-screen top-level window. This allows generating an image from a 3D rendering off-screen.

The function is named grabFramebuffer() for consistency with :sip:ref:`~PyQt6.QtOpenGLWidgets.QOpenGLWidget` and :sip:ref:`~PyQt6.QtQuickWidgets.QQuickWidget`. It is not the only way to get CPU-side image data out of the :sip:ref:`~PyQt6.QtWidgets.QRhiWidget`'s content: calling :sip:ref:`~PyQt6.QtWidgets.QWidget.grab` on a :sip:ref:`~PyQt6.QtWidgets.QRhiWidget`, or an ancestor of it, is functional as well (returning a :sip:ref:`~PyQt6.QtGui.QPixmap`). Besides working directly with :sip:ref:`~PyQt6.QtGui.QImage`, another advantage of grabFramebuffer() is that it may be slightly more performant, simply because it does not have to go through the rest of :sip:ref:`~PyQt6.QtWidgets.QWidget` infrastructure but can right away trigger rendering a new frame and then do the readback.

.. seealso:: :sip:ref:`~PyQt6.QtWidgets.QRhiWidget.setColorBufferFormat`.
