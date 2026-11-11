.. sip:method-description::
    :status: todo
    :pysig: 9674d09315ec457071ca87266af2835d
    :realsig: () const
    :digest: 6513d18c855ecfe434bf6c90293b8dd2

Returns the list of image variables.

These will likely occur in compute shaders. For example, ``layout (binding = 0, rgba8) uniform readonly image2D inputImage;`` generates the following: (shown as textual JSON here)

::

    "storageImages": [
         {
             "binding": 0,
             "imageFormat": "rgba8",
             "name": "inputImage",
             "set": 0,
             "type": "image2D"
         }
     ]

**Note:** Separate image objects are not compatible with some graphics APIs, such as, OpenGL 2.x or OpenGL ES older than 3.1.
