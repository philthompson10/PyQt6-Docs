.. sip:enum-member-description::
    :status: todo
    :value: 49
    :digest: 26794e2d28691d9ea8ecbb24b1cfdaa2

Indicates that ``gl_InstanceIndex`` includes the base instance (the ``firstInstance`` argument in draw calls) in its value. When this feature is unsupported, but BaseInstance is, it indicates that ``gl_InstanceIndex`` always starts at 0, not the base value. In practice this will be the case for Direct 3D 11 and 12 at the moment. With Vulkan and Metal this feature is expected to be reported as supported always. This enum value has been introduced in Qt 6.11.
