.. sip:method-description::
    :status: todo
    :pysig: a3430153ca26a1d7f994339bcda0b964
    :realsig: (const QByteArray&, QByteArray::Base64Options)
    :digest: 5c20c44ce89a8f0d4094147f7128ce3a

Decodes the Base64 array *base64*, using the options defined by *options*. If *options* contains ``IgnoreBase64DecodingErrors`` (the default), the input is not checked for validity; invalid characters in the input are skipped, enabling the decoding process to continue with subsequent characters. If *options* contains ``AbortOnBase64DecodingErrors``, then decoding will stop at the first invalid character.

For example:

.. literalinclude:: ../../../snippets/qtbase-src-corelib-doc-snippets-code-src_corelib_text_qbytearray.py
    :lines: 430-433

The algorithm used to decode Base64-encoded data is defined in RFC 4648.

Returns a QByteArrayFromBase64Result object, containing the decoded data and a flag telling whether decoding was successful. If the ``AbortOnBase64DecodingErrors`` option was passed and the input data was invalid, it is unspecified what the decoded data contains.

.. seealso:: :sip:ref:`~PyQt6.QtCore.QByteArray.toBase64`.
