.. sip:enum-member-description::
    :status: todo
    :value: 7
    :digest: 8dda02854d7b1e2ee00dd59294e16027

Indicates that restarting the assembly of primitives when encountering an index value of 0xFFFF (\ :sip:ref:`~PyQt6.QtGui.QRhiCommandBuffer.IndexFormat.IndexUInt16`) or 0xFFFFFFFF (\ :sip:ref:`~PyQt6.QtGui.QRhiCommandBuffer.IndexFormat.IndexUInt32`) is enabled, for certain primitive topologies at least. :sip:ref:`~PyQt6.QtGui.QRhi` will try to enable this with all backends, but in some cases it will not be supported. Dynamically controlling primitive restart is not possible since with some APIs primitive restart with a fixed index is always on. Applications must assume that whenever this feature is reported as supported, the above mentioned index values ``may`` be treated specially, depending on the topology. The only two topologies where primitive restart is guaranteed to behave identically across backends, as long as this feature is reported as supported, are :sip:ref:`~PyQt6.QtGui.QRhiGraphicsPipeline.Topology.LineStrip` and :sip:ref:`~PyQt6.QtGui.QRhiGraphicsPipeline.Topology.TriangleStrip`.
