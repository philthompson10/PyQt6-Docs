.. sip:class-description::
    :status: todo
    :brief: Authentication object
    :digest: b1c996d1bd7aca5bd13c17f18f7d05a5

The :sip:ref:`~PyQt6.QtNetwork.QAuthenticator` class provides an authentication object.

The :sip:ref:`~PyQt6.QtNetwork.QAuthenticator` class is usually used in the :sip:ref:`~PyQt6.QtNetwork.QNetworkAccessManager.authenticationRequired` and :sip:ref:`~PyQt6.QtNetwork.QNetworkAccessManager.proxyAuthenticationRequired` signals of :sip:ref:`~PyQt6.QtNetwork.QNetworkAccessManager` and :sip:ref:`~PyQt6.QtNetwork.QAbstractSocket`. The class provides a way to pass back the required authentication information to the socket when accessing services that require authentication.

:sip:ref:`~PyQt6.QtNetwork.QAuthenticator` supports the following authentication methods:

* Basic

* NTLM version 2

* Digest-MD5

* SPNEGO/Negotiate

.. _qauthenticator-qauthenticator-options:

.. _qauthenticator-options:

Options
-------

In addition to the username and password required for authentication, a :sip:ref:`~PyQt6.QtNetwork.QAuthenticator` object can also contain additional options. The :sip:ref:`~PyQt6.QtNetwork.QAuthenticator.options` function can be used to query incoming options sent by the server; the :sip:ref:`~PyQt6.QtNetwork.QAuthenticator.setOption` function can be used to set outgoing options, to be processed by the authenticator calculation. The options accepted and provided depend on the authentication type (see method()).

The following tables list known incoming options as well as accepted outgoing options. The list of incoming options is not exhaustive, since servers may include additional information at any time. The list of outgoing options is exhaustive, however, and no unknown options will be treated or sent back to the server.

.. _qauthenticator-basic:

Basic
.....

+-----------+-----------+---------+--------------------------------------------------------------------------------------------------------+
| Option    | Direction | Type    | Description                                                                                            |
+===========+===========+=========+========================================================================================================+
| ``realm`` | Incoming  | QString | Contains the realm of the authentication, the same as :sip:ref:`~PyQt6.QtNetwork.QAuthenticator.realm` |
+-----------+-----------+---------+--------------------------------------------------------------------------------------------------------+

The Basic authentication mechanism supports no outgoing options.

.. _qauthenticator-ntlm-version-2:

NTLM version 2
..............

The NTLM authentication mechanism currently supports no incoming or outgoing options. On Windows, if no *user* has been set, domain``\user`` credentials will be searched for on the local system to enable Single-Sign-On functionality.

.. _qauthenticator-digest-md5:

Digest-MD5
..........

+-----------+-----------+---------+--------------------------------------------------------------------------------------------------------+
| Option    | Direction | Type    | Description                                                                                            |
+===========+===========+=========+========================================================================================================+
| ``realm`` | Incoming  | QString | Contains the realm of the authentication, the same as :sip:ref:`~PyQt6.QtNetwork.QAuthenticator.realm` |
+-----------+-----------+---------+--------------------------------------------------------------------------------------------------------+

The Digest-MD5 authentication mechanism supports no outgoing options.

.. _qauthenticator-spnego-negotiate:

SPNEGO/Negotiate
................

+---------+-----------+---------+------------------------+
| Option  | Direction | Type    | Description            |
+=========+===========+=========+========================+
| ``spn`` | Outgoing  | QString | Provides a custom SPN. |
+---------+-----------+---------+------------------------+

This authentication mechanism currently supports no incoming options.

The ``spn`` property is used on Windows clients when an SSPI library is used. If the property is not set, a default SPN will be used. The default SPN on Windows is ``HTTP/<hostname>``.

Other operating systems use GSSAPI libraries. For that it is expected that KDC is set up, and the credentials can be fetched from it. The backend always uses ``HTTPS@<hostname>`` as an SPN.

.. _qauthenticator-security-considerations:

Security Considerations
-----------------------

:sip:ref:`~PyQt6.QtNetwork.QAuthenticator` stores credentials such as usernames and passwords internally using general-purpose data types (QString, :sip:ref:`~PyQt6.QtCore.QByteArray`) that do not guarantee secure erasure of their contents from memory on destruction. Credential material may persist in freed heap pages, core dumps, swap files, or process memory after a :sip:ref:`~PyQt6.QtNetwork.QAuthenticator` object is destroyed or cleared.

When Basic authentication is negotiated, credentials are transmitted using Base64 encoding, which is trivially reversible. Basic authentication should only be used over TLS-encrypted connections. :sip:ref:`~PyQt6.QtNetwork.QAuthenticator` does not enforce this requirement; applications are responsible for ensuring transport security when Basic authentication is in use.

:sip:ref:`~PyQt6.QtNetwork.QAuthenticator` selects the strongest authentication method offered by the server, using a fixed internal priority order: Negotiate (Kerberos/SPNEGO), NTLM, Digest-MD5, and Basic. The application cannot currently influence this selection or restrict which methods are acceptable. If a server or proxy offers only a weak method, it will be used without notification.

Applications with strict requirements for credential hygiene should take this into account when deciding how and where to use :sip:ref:`~PyQt6.QtNetwork.QAuthenticator`.

.. seealso:: :sip:ref:`~PyQt6.QtNetwork.QSslSocket`.
