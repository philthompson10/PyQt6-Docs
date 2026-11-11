.. sip:method-description::
    :status: todo
    :pysig: c506ff134babdd6e68ab3e6350e95305
    :realsig: () const
    :digest: 6474754f81154005e2f88ce814ad6528

Returns ``true`` if the underlying graphics API has the Y axis pointing up in its normalized device coordinate system.

In practice this is ``false`` for Vulkan only.

**Note:** :sip:ref:`~PyQt6.QtGui.QRhi.clipSpaceCorrMatrix` includes the corresponding adjustment (to make Y point up) in its returned matrix.
