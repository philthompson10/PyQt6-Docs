.. sip:method-description::
    :status: todo
    :pysig: 341be97d9aff90c9978347f66f945b77
    :realsig: () const
    :digest: 6223a804b3c0bcc6785267717be5fe01

Returns the user-agent string sent with HTTP to identify the application.

**Note:** On Windows 8.1 and newer, the default user agent will always report "Windows NT 6.2" (Windows 8), unless the application does contain a manifest that declares newer Windows versions as supported.

.. seealso:: :sip:ref:`~PyQt6.QtWebEngineCore.QWebEngineProfile.setHttpUserAgent`.
