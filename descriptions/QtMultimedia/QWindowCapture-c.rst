.. sip:class-description::
    :status: todo
    :brief: This class is used for capturing a window
    :digest: fffe783524a2466748c16ae146f49982

This class is used for capturing a window.

The class captures a window. It is managed by the :sip:ref:`~PyQt6.QtMultimedia.QMediaCaptureSession` class where the captured window can be displayed in a video preview object or recorded to a file.

The following snippet shows how to select one of the capturable windows and display the result in a :sip:ref:`~PyQt6.QtMultimediaWidgets.QVideoWidget`:

.. literalinclude:: ../../../snippets/qtmultimedia-src-multimedia-doc-snippets-multimedia-snippets-windowcapturesnippets.py
    :lines: 14-27

.. _qwindowcapture-window-capture-limitations:

Window Capture Limitations
--------------------------

The following limitations apply to using :sip:ref:`~PyQt6.QtMultimedia.QWindowCapture`:

* :sip:ref:`~PyQt6.QtMultimedia.QWindowCapture` is only supported with the FFmpeg backend.

* On some platforms, no new video frames are emitted while the captured window content remains unchanged. Applications should therefore not rely on receiving a continuous stream of frames at the requested frame rate.

The following limitations apply when using ``QWindowCapture`` on X11 systems:

* On Linux X11 systems, when a window is moved partially outside the visible screen area, only the visible region is captured. As a result, the emitted video frames may have a size smaller than the window’s geometry.

* Windows that are outside the visible screen area cannot be captured, and an error signal is emitted in that case.

* The behavior of minimized windows or those located on an invisible virtual workspace depends on the window manager. For example, such windows can be captured on GNOME, whereas on WindowMaker or Xfwm such capturing is not allowed, and the window capture instance emits an error.

.. seealso:: :sip:ref:`~PyQt6.QtMultimedia.QMediaCaptureSession`, :sip:ref:`~PyQt6.QtMultimedia.QCapturableWindow`.
