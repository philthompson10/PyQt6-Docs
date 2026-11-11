.. sip:method-description::
    :status: todo
    :pysig: e88157c8fcf2044f2ad16b7a5e46e6b8
    :realsig: (QShader::SerializedFormatVersion) const
    :digest: c0612acc78b65cce0864589b71e6ca13

Returns a serialized binary version of all the data held by the :sip:ref:`~PyQt6.QtGui.QShader`, suitable for writing to files or other I/O devices.

By default the latest serialization format is used. Use *version* parameter to serialize for a compatibility Qt version. Only when it is known that the generated data stream must be made compatible with an older Qt version at the expense of making it incompatible with features introduced since that Qt version, should another value (for example, :sip:ref:`~PyQt6.QtGui.QShader.SerializedFormatVersion.SerializedFormatVersion` for Qt 6.5) be used.

.. seealso:: :sip:ref:`~PyQt6.QtGui.QShader.fromSerialized`.
