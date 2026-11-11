.. sip:method-description::
    :status: todo
    :pysig: a5eebd9700a92503b29e462d7ec8b406
    :realsig: (QByteArrayView) const
    :digest: 3f73db26d4d36e0dc6469664fa73b8b7

Returns ``true`` if *alias* is an alternative name for this timezone.

The IANA (formerly Olson) database has renamed some zones during its history. There are also some zones that only differed prior to 1970 but are now treated as synonymous. Some backends may have data reaching to before 1970 and produce distinct zones in the latter case. Others may produce zones indistinguishable except by :sip:ref:`~PyQt6.QtCore.QTimeZone.id`. This method determines whether an ID refers (at least since 1970) to the same zone that this timezone object describes.

This method is only available when feature ``timezone`` is enabled.

.. seealso:: :sip:ref:`~PyQt6.QtCore.QTimeZone.isTimeZoneIdAvailable`.
