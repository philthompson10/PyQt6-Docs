.. sip:method-description::
    :status: todo
    :pysig: 502f7d3e77c89e5ef63bfbd42eaccbfd
    :realsig: (const QString&) const
    :digest: 0b6c63e41f00d1f7202b321e3dcf4315

Returns ``true`` if there is a query string pair whose key is equal to *key* from the URL.

**Note:** The key expected to be in percent-encoded form. This function will try to recover if an improperly-encoded input is provided, but that may produce data loss. See QUrlQuery#Encoding for more information.

.. seealso:: :sip:ref:`~PyQt6.QtCore.QUrlQuery.addQueryItem`, :sip:ref:`~PyQt6.QtCore.QUrlQuery.queryItemValue`.
