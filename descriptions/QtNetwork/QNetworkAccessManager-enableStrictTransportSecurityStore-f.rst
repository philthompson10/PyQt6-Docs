.. sip:method-description::
    :status: todo
    :pysig: c82d33c2752bf8ce9434e095e2f9cca8
    :realsig: (bool, const QString&)
    :digest: 09357d29857c7bb50f12e0d83bf5f6d6

If *enabled* is ``true``, the internal HSTS cache will use a persistent store to read and write HSTS policies. *storeDir* defines where this store will be located. The default location is defined by :sip:ref:`~PyQt6.QtCore.QStandardPaths.StandardLocation.CacheLocation`. If there is no writable QStandartPaths::CacheLocation and *storeDir* is an empty string, the store will be located in the program's working directory.

**Note:** If HSTS cache already contains HSTS policies by the time persistent store is enabled, these policies will be preserved in the store. In case both cache and store contain the same known hosts, policies from cache are considered to be more up-to-date (and thus will overwrite the previous values in the store). If this behavior is undesired, enable HSTS store before enabling Strict Transport Security. By default, the persistent store of HSTS policies is disabled.

**Note:** The HSTS store persists policies to disk using :sip:ref:`~PyQt6.QtCore.QSettings` in INI format without encryption or integrity protection. The store reveals which hosts the application has communicated with over HTTPS, since an HSTS entry is recorded for each host that sends a Strict-Transport-Security header. In privacy-sensitive applications, this connection history should be treated as confidential data.

An attacker with write access to the store file could remove HSTS entries for specific domains, causing the application to permit plaintext HTTP connections to those domains on subsequent requests and potentially enabling SSL stripping attacks. Applications that rely on HSTS should ensure the store directory is protected by appropriate filesystem permissions.

.. seealso:: :sip:ref:`~PyQt6.QtNetwork.QNetworkAccessManager.isStrictTransportSecurityStoreEnabled`, :sip:ref:`~PyQt6.QtNetwork.QNetworkAccessManager.setStrictTransportSecurityEnabled`, :sip:ref:`~PyQt6.QtCore.QStandardPaths.standardLocations`.
