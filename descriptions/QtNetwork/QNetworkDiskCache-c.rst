.. sip:class-description::
    :status: todo
    :brief: Very basic disk cache
    :digest: 38f00fba2427241eae87a012dad9bd03

The :sip:ref:`~PyQt6.QtNetwork.QNetworkDiskCache` class provides a very basic disk cache.

:sip:ref:`~PyQt6.QtNetwork.QNetworkDiskCache` stores each url in its own file inside of the :sip:ref:`~PyQt6.QtNetwork.QNetworkDiskCache.cacheDirectory` using :sip:ref:`~PyQt6.QtCore.QDataStream`. Files with a text MimeType are compressed using :sip:ref:`~PyQt6.QtCore.qCompress`. Data is written to disk only in :sip:ref:`~PyQt6.QtNetwork.QNetworkDiskCache.insert` and :sip:ref:`~PyQt6.QtNetwork.QNetworkDiskCache.updateMetaData`.

Currently you cannot share the same cache files with more than one disk cache.

:sip:ref:`~PyQt6.QtNetwork.QNetworkDiskCache` by default limits the amount of space that the cache will use on the system to 50MB.

Note you have to set the cache directory before it will work.

A network disk cache can be enabled by:

.. literalinclude:: ../../../snippets/qtbase-src-network-doc-snippets-code-src_network_access_qnetworkdiskcache.py
    :lines: 54-57

When sending requests, to control the preference of when to use the cache and when to use the network, consider the following:

.. literalinclude:: ../../../snippets/qtbase-src-network-doc-snippets-code-src_network_access_qnetworkdiskcache.py
    :lines: 61-68

To check whether the response came from the cache or from the network, the following can be applied:

.. literalinclude:: ../../../snippets/qtbase-src-network-doc-snippets-code-src_network_access_qnetworkdiskcache.py
    :lines: 72-75

.. _qnetworkdiskcache-security-considerations:

Security Considerations
-----------------------

:sip:ref:`~PyQt6.QtNetwork.QNetworkDiskCache` stores HTTP response bodies and metadata, including response headers, to disk without encryption. The compression applied to text content is for storage efficiency only and does not provide confidentiality protection.

Which responses are cached is primarily determined by the HTTP cache control headers sent by the server. Well-configured servers typically prevent caching of responses containing sensitive data from authenticated sessions. However, the application cannot rely on every server doing so correctly, and what the server considers non-sensitive may not match the application's own requirements.

For cases where the server's caching policy is not sufficient:

* Set :sip:ref:`~PyQt6.QtNetwork.QNetworkRequest.Attribute.CacheSaveControlAttribute` to ``false`` on requests whose responses should not be stored.

* Subclass :sip:ref:`~PyQt6.QtNetwork.QAbstractNetworkCache` to implement application-specific filtering of which responses are cached.

Cache entries carry basic structural validation but may become invalid due to disk corruption, unclean application shutdown, or other causes. Applications should not treat cached data as trustworthy without independent validation.
