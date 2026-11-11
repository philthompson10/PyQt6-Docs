.. sip:enum-member-description::
    :status: todo
    :value: 0x1
    :digest: b0497cdb229441bf51dcb7b048f4033d

Indicates that the URL scheme is `potentially trustworthy <https://www.w3.org/TR/powerful-features/#is-origin-trustworthy>`_. This flag should only be applied to URL schemes which ensure data authenticity, confidentiality, and integrity, either through encryption or other means. An examples of secure builtin schemes is ``https`` (authenticated and encrypted) whereas ``http`` is an example of an insecure scheme.
