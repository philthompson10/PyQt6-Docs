.. sip:method-description::
    :status: todo
    :pysig: 9674d09315ec457071ca87266af2835d
    :realsig: () const
    :digest: 08c931fb3aac4c38afb6892b8134f46d

Returns the list of combined image samplers

With GLSL/Vulkan shaders as source a ``layout(binding = 1) uniform sampler2D tex;`` uniform generates the following: (shown as textual JSON here)

::

    "combinedImageSamplers": [
         {
             "binding": 1,
             "name": "tex",
             "set": 0,
             "type": "sampler2D"
         }
     ]

This does not mean that other language versions of the shader must also use a combined image sampler, especially considering that the concept may not exist everywhere. For instance, a HLSL version will likely just use a `Texture2D <https://doc.qt.io/qt-6/qml-qt3d-render-texture2d.html>`_ and SamplerState object with registers t1 and s1, respectively.
