.. sip:enum-description::
    :status: todo
    :digest: 348e344d90621e3ee22334aac5706853

This enum type lists types of URL syntax.

To apply the same-origin policy to a custom URL scheme, WebEngine must be able to compute the origin (host and port combination) of a URL. The ``Host...`` options indicate that the URL scheme conforms to the standard URL syntax (like ``http``) and automatically enable the same-origin policy. The ``Path`` option indicates that the URL scheme uses a non-standard syntax and that the same-origin policy cannot be applied.
