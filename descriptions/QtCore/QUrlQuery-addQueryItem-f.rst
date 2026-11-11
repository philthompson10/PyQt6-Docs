.. sip:method-description::
    :status: todo
    :pysig: 83852cea65251de4eddd3e1a36b61cca
    :realsig: (const QString&, const QString&)
    :digest: 64bc7719a25791bb19b80d77f0020a58

Appends the pair *key* = *value* to the end of the query string of the URL. This method does not overwrite existing items that might exist with the same key.

**Note:** This method does not treat spaces (ASCII 0x20) and plus ("+") signs as the same, like HTML forms do. If you need spaces to be represented as plus signs, use actual plus signs.

**Note:** The key and value strings are expected to be in percent-encoded form. This function will try to recover if improperly-encoded inputs are provided, but that may produce data loss. See QUrlQuery#Encoding for more information.

.. seealso:: :sip:ref:`~PyQt6.QtCore.QUrlQuery.hasQueryItem`, :sip:ref:`~PyQt6.QtCore.QUrlQuery.queryItemValue`.
