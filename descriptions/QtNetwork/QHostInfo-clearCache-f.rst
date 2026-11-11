.. sip:method-description::
    :status: todo
    :pysig: a81259cef8e959c624df1d456e5d3297
    :realsig: ()
    :digest: e17dbab13040a69c2953fac54268ffb5

Clears the internal DNS cache used by :sip:ref:`~PyQt6.QtNetwork.QHostInfo.lookupHost` and :sip:ref:`~PyQt6.QtNetwork.QHostInfo.fromName`.

Call this when cached host information may be stale and fresh lookups are needed. Typical use cases include:

* The application has detected a network configuration change (e.g. switch between Wi-Fi and Ethernet, or VPN connect/disconnect).

* A server's address is known to have changed (e.g. dynamic DNS or failover), and the application should resolve the host name again. Note that upstream DNS servers and resolvers have their own TTL, clearing the cache here does not affect them, so the new lookup may still return the previous address until the upstream TTL expires.

* The application uses a cached result for lookups, but it requires a fresh lookup if the cache has expired or is no longer valid.

This function only clears the cache. It does not cancel in-progress lookups; those will complete and their results will still be delivered. Use this when you want future lookups to resolve again without affecting ongoing operations.

.. seealso:: :sip:ref:`~PyQt6.QtNetwork.QHostInfo.lookupHost`, :sip:ref:`~PyQt6.QtNetwork.QHostInfo.fromName`.
