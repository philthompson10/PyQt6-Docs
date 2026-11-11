.. sip:method-description::
    :status: todo
    :pysig: 8a6768b0f14ec9a0f52992dc52ffb6e4
    :realsig: (QDockWidget*,QDockWidget*)
    :digest: ee38715dd1339695aa14db4479791572

Moves *second* dock widget on top of *first* dock widget, creating a tabbed dock area at the current location of *first*.

Both dock widgets must have been added to the main window with :sip:ref:`~PyQt6.QtWidgets.QMainWindow.addDockWidget` before calling this function, and neither can already be tabbed.

.. seealso:: :sip:ref:`~PyQt6.QtWidgets.QMainWindow.tabifiedDockWidgets`, :sip:ref:`~PyQt6.QtWidgets.QMainWindow.addDockWidget`.
