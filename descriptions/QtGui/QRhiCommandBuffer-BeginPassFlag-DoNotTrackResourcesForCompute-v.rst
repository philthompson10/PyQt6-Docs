.. sip:enum-member-description::
    :status: todo
    :value: 0x02
    :digest: 5d3665170169cb8c2a256a51c3d566ea

Specifies that there is no need to track resources used in this pass if the only purpose of such tracking is to generate barriers for compute. Implies that there are no compute passes in the frame. This is an optimization hint that may be taken into account by certain backends, OpenGL in particular, allowing them to skip certain operations. When this flag is set for a render pass in a frame, calling :sip:ref:`~PyQt6.QtGui.QRhiCommandBuffer.beginComputePass` in that frame may lead to unexpected behavior, depending on the resource dependencies between the render and compute passes.
