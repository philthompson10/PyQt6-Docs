.. sip:enum-member-description::
    :status: todo
    :value: 0x20
    :digest: b35e38206fdbd8056a857a624b4a116b

The item ignores inherited transformations (i.e., its position is still anchored to its parent, but the parent or view rotation, zoom or shear transformations are ignored). This flag is useful for keeping text label items horizontal and unscaled, so they will still be readable if the view is transformed. When set, the item's view geometry and scene geometry will be maintained separately. You must call :sip:ref:`~PyQt6.QtWidgets.QGraphicsItem.deviceTransform` to map coordinates and detect collisions in the view. By default, this flag is disabled. This flag was introduced in Qt 4.3.

**Note:** With this flag set you can still scale the item itself, and that scale transformation will influence the item's children.
