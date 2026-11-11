.. sip:method-description::
    :status: todo
    :pysig: d57c8c7a0b05e01cc5c1d4316a314884
    :realsig: (const QModelIndex&) const
    :digest: 815cd72470ff3146789877ba9c4c4467

Returns the rectangle occupied by the expand/collapse indicator of the item at *index*. If the item has no such indicator, for example because it has no children or because root decoration is disabled, the returned rectangle is invalid. An invalid *index* also returns an invalid rectangle.

.. seealso:: :sip:ref:`~PyQt6.QtWidgets.QTreeView.visualRect`, :sip:ref:`~PyQt6.QtWidgets.QStyle.SubElement.SE_TreeViewDisclosureItem`.
