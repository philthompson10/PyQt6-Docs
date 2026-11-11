.. sip:signal-description::
    :status: todo
    :pysig: 9a8de97bc268eefcf9f170df1b748d31
    :realsig: (const QString&, const QString&, const QUrl&)
    :digest: c636ed721b5f5a46b6440a8437dce4b1

Signal emitted when the authorization server reports an error while processing an authorization or token request, including a token refresh request, as defined in `RFC 6749 error response <https://www.rfc-editor.org/rfc/rfc6749#section-5.2>`_.

*error* is the name of the error; *errorDescription* describes the error and *uri* is an optional URI containing more information about the error.

To catch all errors, including these RFC defined errors, with a single signal, use :sip:ref:`~PyQt6.QtNetworkAuth.QAbstractOAuth.requestFailed`.
