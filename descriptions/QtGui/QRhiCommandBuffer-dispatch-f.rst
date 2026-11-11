.. sip:method-description::
    :status: todo
    :pysig: 883579c2ad1a92ea9bbe04c13915d560
    :realsig: (int, int, int)
    :digest: 01d41376d3f73b8d823d7f46e74b1bdc

Records dispatching compute work items, with *x*, *y*, and *z* specifying the number of local workgroups in the corresponding dimension.

**Note:** This function can only be called inside a compute pass, meaning between a :sip:ref:`~PyQt6.QtGui.QRhiCommandBuffer.beginComputePass` and :sip:ref:`~PyQt6.QtGui.QRhiCommandBuffer.endComputePass` call.

**Note:** *x*, *y*, and *z* must fit the limits from the underlying graphics API implementation at run time. The maximum values are typically 65535.

**Note:** Watch out for possible limits on the local workgroup size as well. This is specified in the shader, for example: ``layout(local_size_x = 16, local_size_y = 16) in;``. For example, with OpenGL the minimum value mandated by the specification for the number of invocations in a single local work group (the product of ``local_size_x``, ``local_size_y``, and ``local_size_z``) is 1024, while with OpenGL ES (3.1) the value may be as low as 128. This means that the example given above may be rejected by some OpenGL ES implementations as the number of invocations is 256.
