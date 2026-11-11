.. sip:method-description::
    :status: todo
    :pysig: eea82972cfc19f9f41f0da4f56505671
    :realsig: (const QMetaObject::Connection&)
    :digest: 7ef793355b10fbcf98d3a78174ccc9af

Disconnects *connection* and resets it to invalid.

If *connection* is invalid or has already been disconnected, do nothing and return false.

**Note:** Future versions of Qt may only accept non-const objects here.

.. seealso:: QT_NO_DISCONNECT_CONST_CONNECTION, connect().
