.. sip:method-description::
    :status: todo
    :pysig: cb302762723c29c5461471dab9eef185
    :realsig: (int, int, QRhiVertexInputAttribute::Format, quint32, int)
    :digest: 137467dd26cbb549e3ae4cd8163f9049

Constructs a vertex input attribute description with the specified *binding* number, *location*, *format*, and *offset*.

*matrixSlice* should be -1 except when this attribute corresponds to a row or column of a matrix (for example, a 4x4 matrix becomes 4 vec4s, consuming 4 consecutive vertex input locations), in which case it is the index of the row or column. ``location - matrixSlice`` must always be equal to the ``location`` for the first row or column of the unrolled matrix.
