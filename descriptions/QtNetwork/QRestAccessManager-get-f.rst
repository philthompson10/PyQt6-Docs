.. sip:method-description::
    :status: todo
    :pysig: b567d01f49ed6b4a87887827b8091a7a
    :realsig: (const QNetworkRequest&)
    :digest: e590c379aadb455152649c9b3d9df114

Issues an ``HTTP GET`` based on *request*.

The optional *callback* and *context* object can be provided for handling the request completion as illustrated below:

.. literalinclude:: ../../../snippets/qtbase-src-network-doc-snippets-code-src_network_access_qrestaccessmanager.py
    :lines: 44-49

Alternatively the signals of the returned :sip:ref:`~PyQt6.QtNetwork.QNetworkReply`\* object can be used. For further information see :ref:`qrestaccessmanager-issuing-network-requests-and-handling-replies`.

.. seealso:: :sip:ref:`~PyQt6.QtNetwork.QRestReply`.
