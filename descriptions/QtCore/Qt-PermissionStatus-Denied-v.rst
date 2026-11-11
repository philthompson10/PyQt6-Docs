.. sip:enum-member-description::
    :status: todo
    :value: 2
    :digest: f850d915a0b08e5528e74bad57209330

The user has explicitly denied the application the requested permission, or the permission is known to not be accessible or applicable to applications on the given platform.

**Note:** On Android, there is no ``Undetermined`` status by the platform's APIs. Thus, if a permission is denied for an app, :sip:ref:`~PyQt6.QtCore.QCoreApplication.checkPermission` returns ``Undetermined`` by default until :sip:ref:`~PyQt6.QtCore.QCoreApplication.requestPermission` is called. After that :sip:ref:`~PyQt6.QtCore.QCoreApplication.checkPermission` reports a non ``Undetermined`` status.
