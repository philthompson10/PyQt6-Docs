.. sip:method-description::
    :status: todo
    :pysig: 12fa34a8fc679aa7d3a01c75261459cc
    :realsig: (int,QAbstractAnimation*)
    :digest: 842bbaf87990df1f74e1454b7aa7f51f

Inserts *animation* into this animation group at *index*. If *index* is 0 the animation is inserted at the beginning. If *index* is :sip:ref:`~PyQt6.QtCore.QAnimationGroup.animationCount`, the animation is inserted at the end.

**Note:** The group takes ownership of the animation.

**Warning:** This method does not check for animation loops. It's the developer's responsibility to make sure that the added *animation* does not include ``this`` animation group directly or indirectly.

.. seealso:: :sip:ref:`~PyQt6.QtCore.QAnimationGroup.takeAnimation`, :sip:ref:`~PyQt6.QtCore.QAnimationGroup.addAnimation`, :sip:ref:`~PyQt6.QtCore.QAnimationGroup.indexOfAnimation`, :sip:ref:`~PyQt6.QtCore.QAnimationGroup.removeAnimation`.
