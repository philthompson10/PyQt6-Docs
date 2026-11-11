.. sip:method-description::
    :status: todo
    :pysig: c21c9b9de14a7fefe00f2a9acd16a276
    :realsig: () const
    :digest: 954e47812d5c8c424265bba4f33167b4

Returns the list of shader storage blocks.

For example, with GLSL/Vulkan shaders as source, the declaration

::

    struct Stuff {
        vec2 a;
        vec2 b;
    };
    layout(std140, binding = 0) buffer StuffSsbo {
        vec4 whatever;
        Stuff stuff[];
    } buf;

generates the following: (shown as textual JSON here)

::

    "storageBlocks": [ {
        "binding": 0,
        "blockName": "StuffSsbo",
        "instanceName": "buf",
        "knownSize": 16,
        "runtimeArrayStride": 16
        "members": [
            {
                "name": "whatever",
                "offset": 0,
                "size": 16,
                "type": "vec4"
            },
            {
                "arrayDims": [
                    0
                ],
                "name": "stuff",
                "offset": 16,
                "size": 0,
                "structMembers": [
                    {
                        "name": "a",
                        "offset": 0,
                        "size": 8,
                        "type": "vec2"
                    },
                    {
                        "name": "b",
                        "offset": 8,
                        "size": 8,
                        "type": "vec2"
                    }
                ],
                "type": "struct"
            }
        ],
        "set": 0
    } ]

**Note:** The size of the last member in the storage block is undefined. This shows up as ``size`` 0 and an array dimension of ``[0]``. The storage block's ``knownSize`` excludes the size of the last member since that will only be known at run time. The stride in bytes between array items for a last member with undefined array size is ``runtimeArrayStride``. This value is determined according to the specified buffer memory layout standard (std140, std430) rules.

**Note:** SSBOs are not available with some graphics APIs, such as, OpenGL 2.x or OpenGL ES older than 3.1.
