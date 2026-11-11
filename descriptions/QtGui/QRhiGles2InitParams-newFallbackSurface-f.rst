.. sip:method-description::
    :status: todo
    :pysig: f4b25741c178ebefbf1a6b1b3d79643c
    :realsig: (const QSurfaceFormat&)
    :digest: 1acbe61842adf49a8650c7e9755e816f

Returns a new :sip:ref:`~PyQt6.QtGui.QOffscreenSurface` that can be used with a :sip:ref:`~PyQt6.QtGui.QRhi` by passing it via a :sip:ref:`~PyQt6.QtGui.QRhiGles2InitParams`.

When *format* is not specified, its default value is the global default format settable via :sip:ref:`~PyQt6.QtGui.QSurfaceFormat.setDefaultFormat`.

*format* is adjusted as appropriate in order to avoid having problems afterwards due to an incompatible context and surface.

**Note:** This function must only be called on the gui/main thread or if the platform integration supports offscreen surfaces.

**Note:** It is the application's responsibility to destroy the returned :sip:ref:`~PyQt6.QtGui.QOffscreenSurface` on the gui/main thread once the associated :sip:ref:`~PyQt6.QtGui.QRhi` has been destroyed. The :sip:ref:`~PyQt6.QtGui.QRhi` will not destroy the :sip:ref:`~PyQt6.QtGui.QOffscreenSurface`.
