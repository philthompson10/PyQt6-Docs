.. sip:method-description::
    :status: todo
    :pysig: c506ff134babdd6e68ab3e6350e95305
    :realsig: () const
    :digest: 74b931cc0cf3885b6cd46834d275ba49

Returns ``true`` if the system backend supports obtaining transitions.

Transitions are changes in the time-zone: these happen when DST turns on or off and when authorities alter the offsets for the time-zone.

This method is only available when feature ``timezone`` is enabled.

**Note:** this is not a property of the timezone described by this object but of the backend that provides data about the zone, typically from system libraries. It tells you whether the other transition-related functions have anything to offer.

.. seealso:: :sip:ref:`~PyQt6.QtCore.QTimeZone.nextTransition`, :sip:ref:`~PyQt6.QtCore.QTimeZone.previousTransition`, :sip:ref:`~PyQt6.QtCore.QTimeZone.transitions`.
