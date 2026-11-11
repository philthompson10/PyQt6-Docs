.. sip:method-description::
    :status: todo
    :pysig: 27b8bac486eb33066f530893cf5e1bcc
    :realsig: (QAbstractAnimation*)
    :digest: 0c839e41e1244eacd4e53e7b058e248c

Adds *animation* to this group. This will call :sip:ref:`~PyQt6.QtCore.QAnimationGroup.insertAnimation` with index equals to :sip:ref:`~PyQt6.QtCore.QAnimationGroup.animationCount`.

**Note:** The group takes ownership of the animation.

**Warning:** This method does not check for animation loops. It's the developer's responsibility to make sure that the added *animation* does not include ``this`` animation group directly or indirectly.

.. seealso:: :sip:ref:`~PyQt6.QtCore.QAnimationGroup.removeAnimation`.
