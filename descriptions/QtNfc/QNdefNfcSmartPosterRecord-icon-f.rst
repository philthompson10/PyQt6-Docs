.. sip:method-description::
    :status: todo
    :pysig: 180c3b1472c7366993c7351f52cb1362
    :realsig: (const QByteArray&) const
    :digest: 08185a5ff6fb4e49dd139b631861ab12

Returns the associated icon record data if the smart poster contains an icon record with MIME type *mimetype*. If *mimetype* is omitted or empty then the first icon's record data is returned. In all other cases, an empty array is returned.

**Warning:** Application developers are advised to validate the returned data before processing it. See Qt NFC Security Considerations for guidance.
