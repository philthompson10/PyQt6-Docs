.. sip:method-description::
    :status: todo
    :pysig: 464116456943d857ef223b2d24ec328b
    :realsig: (const QString&)
    :digest: aed22db25ca96eb95e6f80d3a2f005f8

Removes the query string pair whose key is equal to *key* from the URL. If there are multiple items with a key equal to *key*, it removes the first item in the order they were present in the query string or added with :sip:ref:`~PyQt6.QtCore.QUrlQuery.addQueryItem`.

**Note:** The key is expected to be in percent-encoded form. This function will try to recover if an improperly-encoded input is provided, but that may produce data loss. See QUrlQuery#Encoding for more information.

.. seealso:: :sip:ref:`~PyQt6.QtCore.QUrlQuery.removeAllQueryItems`.
