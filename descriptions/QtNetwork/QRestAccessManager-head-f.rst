.. sip:method-description::
    :status: todo
    :pysig: b567d01f49ed6b4a87887827b8091a7a
    :realsig: (const QNetworkRequest&)
    :digest: 0165e4793590238adc8e1826b1142ba5

Issues an ``HTTP HEAD`` based on *request*.

The optional *callback* and *context* object can be provided for handling the request completion as illustrated below:

.. literalinclude:: ../../../snippets/qtbase-src-network-doc-snippets-code-src_network_access_qrestaccessmanager.py
    :lines: 78-81

Alternatively the signals of the returned :sip:ref:`~PyQt6.QtNetwork.QNetworkReply`\* object can be used. For further information see :ref:`qrestaccessmanager-issuing-network-requests-and-handling-replies`.

``head()`` request does not support providing data.

.. seealso:: :sip:ref:`~PyQt6.QtNetwork.QRestReply`.
