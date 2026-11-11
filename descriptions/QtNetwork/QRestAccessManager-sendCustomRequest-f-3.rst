.. sip:method-description::
    :status: todo
    :pysig: 9594c1c267ac813443080157677d57fd
    :realsig: (const QNetworkRequest&, const QByteArray&, const QByteArray&)
    :digest: 525638cba13ccd48a7662d2d25b3e0e4

Issues *request* based HTTP request with custom *method* and the provided *data*.

The optional *callback* and *context* object can be provided for handling the request completion as illustrated below:

.. literalinclude:: ../../../snippets/qtbase-src-network-doc-snippets-code-src_network_access_qrestaccessmanager.py
    :lines: 94-97

Alternatively the signals of the returned :sip:ref:`~PyQt6.QtNetwork.QNetworkReply`\* object can be used. For further information see :ref:`qrestaccessmanager-issuing-network-requests-and-handling-replies`.
