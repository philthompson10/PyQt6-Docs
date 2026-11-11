.. sip:enum-member-description::
    :status: todo
    :value: 1 << 4
    :digest: 8fe474eaf0c523329b3a219fa2ae4cba

Indicates that a per-draw (per-pipeline) shading rate value will be set via :sip:ref:`~PyQt6.QtGui.QRhiCommandBuffer.setShadingRate`. Not specifying this flag and still calling setShadingRate() may lead to varying, unexpected results depending on the underlying graphics API.
