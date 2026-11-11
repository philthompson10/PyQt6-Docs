.. sip:method-description::
    :status: todo
    :pysig: fa7153f7ed1cb6c0fcf2ffb2fac21748
    :realsig: () const
    :digest: aa58e7d8f0a9f44967082bf89d203536

Returns the total and effective duration of the animation, including the loop count.

**Note:** If the loop count is very large, or if the duration of a single loop is too long, the total duration can be too large to fit into an ``int``. In such case the value is saturated to ``INT_MAX``.

.. seealso:: :sip:ref:`~PyQt6.QtCore.QAbstractAnimation.duration`, :sip:ref:`~PyQt6.QtCore.QAbstractAnimation.currentTime`.
