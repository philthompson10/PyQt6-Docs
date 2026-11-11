.. sip:method-description::
    :status: todo
    :pysig: bee1421cc7066b77895be85d5861066e
    :realsig: (const QNetworkRequest&, const QJsonDocument&)
    :digest: c278c695ba35b4ce39fb4748f5b645d0

Issues an ``HTTP POST`` based on *request*.

The optional *callback* and *context* object can be provided for handling the request completion as illustrated below:

.. literalinclude:: ../../../snippets/qtbase-src-network-doc-snippets-code-src_network_access_qrestaccessmanager.py
    :lines: 62-65

Alternatively, the signals of the returned :sip:ref:`~PyQt6.QtNetwork.QNetworkReply`\* object can be used. For further information see :ref:`qrestaccessmanager-issuing-network-requests-and-handling-replies`.

The ``post()`` method always requires *data* parameter. The following data types are supported:

* :sip:ref:`~PyQt6.QtCore.QByteArray`

* :sip:ref:`~PyQt6.QtCore.QJsonDocument` \*)

* QVariantMap \*\*)

* :sip:ref:`~PyQt6.QtNetwork.QHttpMultiPart`\*

* :sip:ref:`~PyQt6.QtCore.QIODevice`\*

\*) Sent in :sip:ref:`~PyQt6.QtCore.QJsonDocument.JsonFormat.Compact` format, and the ``Content-Type`` header is set to ``application/json`` if the ``Content-Type`` header was not set \*\*) QVariantMap is converted to and treated as a QJsonObject

.. seealso:: :sip:ref:`~PyQt6.QtNetwork.QRestReply`.
