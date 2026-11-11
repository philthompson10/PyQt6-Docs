.. sip:enum-member-description::
    :status: todo
    :value: 26
    :digest: d9d887de68bc41b2ea63136368ed9e7f

Signed short (16 bit) integer

**Note:** Support for half precision floating point attributes is indicated at run time by the :sip:ref:`~PyQt6.QtGui.QRhi.Feature.HalfAttributes` feature flag.

**Note:** Direct3D 11/12 supports 16 bit input attributes, but does not support the Half3, UShort3 or SShort3 types. The D3D backends pass through Half3 as Half4, UShort3 as UShort4, and SShort3 as SShort4. To ensure cross platform compatibility, 16 bit inputs should be padded to 8 bytes.
