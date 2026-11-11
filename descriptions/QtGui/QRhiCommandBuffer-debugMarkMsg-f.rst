.. sip:method-description::
    :status: todo
    :pysig: c70916e782d9742b90f37ccdedc4f900
    :realsig: (const QByteArray&)
    :digest: 17967073a76dce152051b3eed94e7d47

Inserts a debug message *msg* into the command stream.

**Note:** Ignored when :sip:ref:`~PyQt6.QtGui.QRhi.Feature.DebugMarkers` are not supported or :sip:ref:`~PyQt6.QtGui.QRhi.Flag.EnableDebugMarkers` is not set.

**Note:** With some backends debugMarkMsg() is only supported inside a pass and is ignored when called outside a pass. With others it is recorded anywhere within the frame.
