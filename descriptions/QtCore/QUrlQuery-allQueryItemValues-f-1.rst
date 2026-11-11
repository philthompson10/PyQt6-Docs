.. sip:method-description::
    :status: todo
    :pysig: 144a6f861de71103f482b5ab421a1a90
    :realsig: (const QString&, QUrl::ComponentFormattingOptions) const
    :digest: 30e9fe3e3479ca37461a5a59365c7dcf

Returns the a list of query string values whose key is equal to *key* from the URL, using the options specified in *encoding* to encode the return value. If the key *key* is not found, this function returns an empty list.

**Note:** The key is expected to be in percent-encoded form. This function will try to recover if an improperly-encoded input is provided, but that may produce data loss. See QUrlQuery#Encoding for more information.

.. seealso:: :sip:ref:`~PyQt6.QtCore.QUrlQuery.queryItemValue`, :sip:ref:`~PyQt6.QtCore.QUrlQuery.addQueryItem`.
