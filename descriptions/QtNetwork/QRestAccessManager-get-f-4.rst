.. sip:method-description::
    :status: todo
    :pysig: 20107dd75f13112f5ee3b0379f478d95
    :realsig: (const QNetworkRequest&, const QByteArray&)
    :digest: 15ea7f2f77b1e73ffd9926c137a606c4

Issues an ``HTTP GET`` based on *request* and provided *data*.

The optional *callback* and *context* object can be provided for handling the request completion as illustrated below:

.. literalinclude:: ../../../snippets/qtbase-src-network-doc-snippets-code-src_network_access_qrestaccessmanager.py
    :lines: 54-57

Alternatively the signals of the returned :sip:ref:`~PyQt6.QtNetwork.QNetworkReply`\* object can be used. For further information see :ref:`qrestaccessmanager-issuing-network-requests-and-handling-replies`.

.. seealso:: :sip:ref:`~PyQt6.QtNetwork.QRestReply`.
