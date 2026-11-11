.. sip:enum-member-description::
    :status: todo
    :value: 17
    :digest: a8e367d7b056b02b0b33ef6a3f931d84

Indicates that instanced draw commands support the ``firstInstance`` argument. When reported as not supported, the firstInstance value is ignored and the instance ID starts from 0. In practice this feature will be unsupported with Metal on older iOS devices, including the iOS Simulator, and all versions of OpenGL. The latter is due to OpenGL ES not supporting draw calls with a base instance at all. Currently :sip:ref:`~PyQt6.QtGui.QRhi`'s OpenGL backend does not implement the functionality for OpenGL (non-ES) either, because portable applications cannot rely on a non-zero base instance in practice due to GLES. If the application still chooses to do so, it should be aware of the InstanceIndexIncludesBaseInstance feature as well.
