.. sip:enum-member-description::
    :status: todo
    :value: 36
    :digest: 9ed205b0c4a9f4e2b101fdc93072e685

The color format is considered as ASTC compressed format with 12x12 block footprint.

**Note:** With the exception of ``RGBA8``, not every format is supported at runtime as this depends on which backend is being used as well which hardware is being used.

**Note:** ``RGBE`` is internally represented as an ``RGBA8`` but is intepreted as described when used as a lightProbe or skybox texture.

**Note:** Using the value ``None`` will assume the default value of ``RGBA8``
