.. sip:method-description::
    :status: todo
    :pysig: 4d198984cda037ae24fe3f5112568937
    :realsig: (const QModelIndex&,const QModelIndex&) const
    :digest: 851b053eb47ad91476c07614f478eb08

Returns ``true`` if the value of the item referred to by the given index *source_left* is less than the value of the item referred to by the given index *source_right*, otherwise returns ``false``.

This function is used as the ``operator<`` when sorting, and uses QAbstractItemModel::compareData().

Comparison of QStrings is case sensitive by default; this can be changed using the :sip:ref:`~PyQt6.QtCore.QSortFilterProxyModel.sortCaseSensitivity` property.

By default, the :sip:ref:`~PyQt6.QtCore.Qt.ItemDataRole.DisplayRole` associated with the :sip:ref:`~PyQt6.QtCore.QModelIndex`\ es is used for comparisons. This can be changed by setting the :sip:ref:`~PyQt6.QtCore.QSortFilterProxyModel.sortRole` property.

**Note:** The indices passed in correspond to the source model.

.. seealso:: :sip:ref:`~PyQt6.QtCore.QSortFilterProxyModel.sortRole`, :sip:ref:`~PyQt6.QtCore.QSortFilterProxyModel.sortCaseSensitivity`, :sip:ref:`~PyQt6.QtCore.QSortFilterProxyModel.dynamicSortFilter`.
