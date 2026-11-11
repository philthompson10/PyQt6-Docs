.. sip:method-description::
    :status: todo
    :pysig: 464116456943d857ef223b2d24ec328b
    :realsig: (const QString&)
    :digest: 0bb53f1e42f9dae8940e7ede8c58c25a

Removes all the query string pairs whose key is equal to *key* from the URL.

**Note:** The key is expected to be in percent-encoded form. This function will try to recover if an improperly-encoded input is provided, but that may produce data loss. See QUrlQuery#Encoding for more information.

.. seealso:: :sip:ref:`~PyQt6.QtCore.QUrlQuery.removeQueryItem`.
