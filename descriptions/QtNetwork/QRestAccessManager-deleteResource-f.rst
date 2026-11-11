.. sip:method-description::
    :status: todo
    :pysig: b567d01f49ed6b4a87887827b8091a7a
    :realsig: (const QNetworkRequest&)
    :digest: 89de8571ae7cc3ab272e4cbee98145c3

Issues an ``HTTP DELETE`` based on *request*.

The optional *callback* and *context* object can be provided for handling the request completion as illustrated below:

.. literalinclude:: ../../../snippets/qtbase-src-network-doc-snippets-code-src_network_access_qrestaccessmanager.py
    :lines: 86-89

Alternatively the signals of the returned :sip:ref:`~PyQt6.QtNetwork.QNetworkReply`\* object can be used. For further information see :ref:`qrestaccessmanager-issuing-network-requests-and-handling-replies`.

``deleteResource()`` request does not support providing data.

.. seealso:: :sip:ref:`~PyQt6.QtNetwork.QRestReply`.
