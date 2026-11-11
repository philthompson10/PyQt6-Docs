.. sip:method-description::
    :status: todo
    :pysig: 469ad8964f9f18fcdfc5f7b15675dddf
    :realsig: (const QList<std::pair<QString, QString>>&)
    :digest: c61219300b85303db7ce32dcd353102e

Sets the items in this :sip:ref:`~PyQt6.QtCore.QUrlQuery` object to *query*. The order of the elements in *query* is preserved.

**Note:** This method does not treat spaces (ASCII 0x20) and plus ("+") signs as the same, like HTML forms do. If you need spaces to be represented as plus signs, use actual plus signs.

**Note:** The keys and values are expected to be in percent-encoded form. This function will try to recover if improperly-encoded inputs are provided, but that may produce data loss. See QUrlQuery#Encoding for more information.

.. seealso:: :sip:ref:`~PyQt6.QtCore.QUrlQuery.queryItems`, :sip:ref:`~PyQt6.QtCore.QUrlQuery.isEmpty`.
