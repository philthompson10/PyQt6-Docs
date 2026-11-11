.. sip:enum-member-description::
    :status: todo
    :value: 3
    :digest: 3600fea6aab345c9923be685e1144233

Client decides whether to follow each redirect by handling the redirected() signal, emitting redirectAllowed() on the :sip:ref:`~PyQt6.QtNetwork.QNetworkReply` object to allow the redirect or aborting/finishing it to reject the redirect. This can be used, for example, to ask the user whether to accept the redirect, or to decide based on some app-specific configuration.

**Note:** When Qt handles redirects it will, for legacy and compatibility reasons, issue the redirected request using GET when the server returns a 301 or 302 response, regardless of the original method used, unless it was HEAD.
