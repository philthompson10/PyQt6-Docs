.. sip:signal-description::
    :status: todo
    :pysig: 9a8de97bc268eefcf9f170df1b748d31
    :realsig: (const QString&, const QString&, const QUrl&)
    :digest: c14f3c84088276704a90c7f87f3ee93f

Use :sip:ref:`~PyQt6.QtNetworkAuth.QAbstractOAuth2.serverReportedErrorOccurred` instead

Signal emitted when the authorization server reports an error while processing an authorization or token request, including a token refresh request, as defined in `RFC 6749 error response <https://www.rfc-editor.org/rfc/rfc6749#section-5.2>`_.

*error* is the name of the error; *errorDescription* describes the error and *uri* is an optional URI containing more information about the error.

.. seealso:: :sip:ref:`~PyQt6.QtNetworkAuth.QAbstractOAuth.requestFailed`, :sip:ref:`~PyQt6.QtNetworkAuth.QAbstractOAuth2.serverReportedErrorOccurred`.
