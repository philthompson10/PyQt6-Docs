.. sip:method-description::
    :status: todo
    :pysig: fbca27280a0dea103a21e10a55473713
    :realsig: (const QModelIndex&, const QModelIndex&, const QList<int>&) const
    :digest: 19b0603e66401996a54430b2bd0a50c3

Reimplement this slot in a subclass to indicate when a source model change is relevant for filtering or sorting. It is used as a performance optimization to avoid unnecessary :sip:ref:`~PyQt6.QtCore.QSortFilterProxyModel.filterAcceptsRow` and :sip:ref:`~PyQt6.QtCore.QSortFilterProxyModel.lessThan` calls upon source model changes that do not affect the sorting and filtering results. The *sourceTopLeft*, *sourceBottomRight* and *roles* parameters are those emitted by the source model's dataChanged() signal corresponding to the change being evaluated for relevance.

**Note:** Because of binary compatibility constraints, this method can't be virtual until Qt 7. Meanwhile, redeclare it in a subclass as a slot or Q_INVOKABLE method and :sip:ref:`~PyQt6.QtCore.QSortFilterProxyModel` will dynamically detect and invoke it.

**Note:** The default implementation assumes that any change is relevant for filtering, and only changes in the source sort column are relevant for sorting.

.. seealso:: DataChangeRelevanceFlags, :sip:ref:`~PyQt6.QtCore.QSortFilterProxyModel.filterAcceptsRow`, :sip:ref:`~PyQt6.QtCore.QSortFilterProxyModel.lessThan`.
