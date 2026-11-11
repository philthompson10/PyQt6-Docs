.. sip:method-description::
    :status: todo
    :pysig: c70916e782d9742b90f37ccdedc4f900
    :realsig: (QByteArrayView)
    :digest: e8cca299e869541914979bf4b655c4ec

Appends the byte array *ba* to the stream, creating a CBOR Byte String value. :sip:ref:`~PyQt6.QtCore.QCborStreamWriter` will attempt to write the entire string in one chunk.

The following example will load and append the contents of a file to the stream:

.. literalinclude:: ../../../snippets/qtbase-src-corelib-doc-snippets-code-src_corelib_serialization_qcborstream.py
    :lines: 114-119

As the example shows, unlike JSON, CBOR requires no escaping for binary content.

**Note:** The overload taking a QByteArrayView has been present since Qt 6.10.

.. seealso:: appendByteString(), :sip:ref:`~PyQt6.QtCore.QCborStreamReader.isByteArray`, :sip:ref:`~PyQt6.QtCore.QCborStreamReader.readByteArray`.
