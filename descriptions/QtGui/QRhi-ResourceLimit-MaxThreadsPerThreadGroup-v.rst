.. sip:enum-member-description::
    :status: todo
    :value: 7
    :digest: 028eb5c6b5039b1e24830ec2d0d874fc

The maximum number of invocations in a single local work group, or in other terminology, the maximum number of threads in a thread group. Effectively the maximum value for the product of ``local_size_x``, ``local_size_y``, and ``local_size_z`` in the compute shader. Typical values are 128, 256, 512, 1024, or 1536. Watch out that both OpenGL ES and Vulkan specify only 128 as the minimum required limit for implementations. While uncommon for Vulkan, some OpenGL ES 3.1 implementations for mobile/embedded devices only support the spec-mandated minimum value.
