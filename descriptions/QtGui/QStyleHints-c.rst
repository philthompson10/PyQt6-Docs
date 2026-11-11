.. sip:class-description::
    :status: todo
    :brief: Contains platform specific hints and settings
    :digest: bb36a486f480bc09a7a273a42d671669

The :sip:ref:`~PyQt6.QtGui.QStyleHints` class contains platform specific hints and settings.

An object of this class, obtained from :sip:ref:`~PyQt6.QtGui.QGuiApplication`, provides access to certain global user interface parameters of the current platform.

The platform provides most of these settings, and they are typically read-only. End users can usually adjust them through platform-specific configuration mechanisms. However, you can also adjust some settings programmatically through dedicated setter functions, (for example, :sip:ref:`~PyQt6.QtGui.QStyleHints.setColorScheme` or :sip:ref:`~PyQt6.QtGui.QStyleHints.setShowShortcutsInContextMenus`), which can be useful for testing or specialized application behavior. Any such adjustments apply only to the current application.

Authors of custom user interface components should read relevant settings to allow the components to exhibit the same behavior and feel as other components.

.. seealso:: :sip:ref:`~PyQt6.QtGui.QGuiApplication.styleHints`.
