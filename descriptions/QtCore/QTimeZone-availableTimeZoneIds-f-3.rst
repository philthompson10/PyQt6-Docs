.. sip:method-description::
    :status: todo
    :pysig: 95bc3d14303f22e358f6ff12558385a3
    :realsig: ()
    :digest: 289c0da144b44f6aaf203ad402f9fc3c

Returns a list of available time zone IDs on this system.

This includes an IANA ID for each zone supported by the system timezone information source, plus some aliases of these and a limited set of commonly-used UTC-offset IDs.

The :sip:ref:`~PyQt6.QtCore.QTimeZone` constructor will also accept some UTC-offset IDs that are not in the list returned - it would be impractical to list all possible UTC-offset IDs. It also accepts known aliases for supported IANA IDs, some of which may not appear in this list. Such IDs are also accepted by :sip:ref:`~PyQt6.QtCore.QTimeZone.isTimeZoneIdAvailable`.

Where the Unicode Consortium's Common Locale Data Repository (CLDR) regards a supported IANA ID as an alias for its stable name for the zone, this stable name for the zone is also included in the list (even though it may be out of date), both for stability and as cross-platform common ground where different system timezone information sources use different aliases for the same zone.

This method is only available when feature ``timezone`` is enabled.

.. seealso:: :sip:ref:`~PyQt6.QtCore.QTimeZone.isTimeZoneIdAvailable`, :sip:ref:`~PyQt6.QtCore.QTimeZone.hasAlternativeName`.
