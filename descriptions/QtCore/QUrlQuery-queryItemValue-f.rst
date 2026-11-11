.. sip:method-description::
    :status: todo
    :pysig: c0fb5dccee940df307e86ef88a006ff1
    :realsig: (const QString&, QUrl::ComponentFormattingOptions) const
    :digest: ad0ddd01aebf885224d57160ae7853f4

Returns the query value associated with key *key* from the URL, using the options specified in *encoding* to encode the return value. If the key *key* is not found, this function returns an empty string. If you need to distinguish between an empty value and a non-existent key, you should check for the key's presence first using :sip:ref:`~PyQt6.QtCore.QUrlQuery.hasQueryItem`.

If the key *key* is multiply defined, this function will return the first one found, in the order they were present in the query string or added using :sip:ref:`~PyQt6.QtCore.QUrlQuery.addQueryItem`.

**Note:** The key is expected to be in percent-encoded form. This function will try to recover if an improperly-encoded input is provided, but that may produce data loss. See QUrlQuery#Encoding for more information.

.. seealso:: :sip:ref:`~PyQt6.QtCore.QUrlQuery.addQueryItem`, :sip:ref:`~PyQt6.QtCore.QUrlQuery.allQueryItemValues`, `Encoding <https://doc.qt.io/qt-6/string-processing.html#encoding>`_.
