.. sip:enum-member-description::
    :status: todo
    :value: 0x10
    :digest: b00217f89cc8aa23b4ac57830794277b

The item clips the painting of all its descendants to its own shape. Items that are either direct or indirect children of this item cannot draw outside this item's shape. By default, this flag is disabled; children can draw anywhere. This behavior is enforced by QGraphicsView::drawItems() or QGraphicsScene::drawItems(). This flag was introduced in Qt 4.3.

**Note:** This flag is similar to ItemContainsChildrenInShape but in addition enforces the containment by clipping the children.
