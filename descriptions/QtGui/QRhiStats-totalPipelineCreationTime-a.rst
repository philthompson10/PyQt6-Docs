.. sip:attribute-description::
    :status: todo
    :digest: dc37e1402ed2164aaa281409adf96b0b

The total time in milliseconds spent in graphics and compute pipeline creation, which usually involves shader compilation or cache lookups, and potentially expensive processing.

**Note:** The value should not be compared between different backends since the concept of "pipelines" and what exactly happens under the hood during, for instance, a call to QRhiGraphicsPipeline::create(), differ greatly between graphics APIs and their implementations.

.. seealso:: :sip:ref:`~PyQt6.QtGui.QRhi.statistics`.
