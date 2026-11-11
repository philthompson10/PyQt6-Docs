.. sip:method-description::
    :status: todo
    :pysig: d41d8cd98f00b204e9800998ecf8427e
    :realsig: ()
    :digest: aa28d3f527b7b60277d260ee45cbaf54

Schedules dropping unused textures from the cache.

Additionally, other caches and pools may get shrunk upon calling this function, in order to minimize memory usage. This may potentially lead to more expensive drawing calls afterwards.
