.. sip:enum-member-description::
    :status: todo
    :value: 1 << 4
    :digest: 69d57348f216df224e6eaa84c84fc7fd

Requests disabling waiting for vertical sync, also avoiding throttling the rendering thread. The behavior is backend specific and applicable only where it is possible to control this. Some may ignore the request altogether. For OpenGL, try instead setting the swap interval to 0 on the :sip:ref:`~PyQt6.QtGui.QWindow` via :sip:ref:`~PyQt6.QtGui.QSurfaceFormat.setSwapInterval`.
