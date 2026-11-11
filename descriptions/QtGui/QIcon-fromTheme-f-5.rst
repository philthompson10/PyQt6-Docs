.. sip:method-description::
    :status: todo
    :pysig: 331ad674cda68893946f7b55a48defec
    :realsig: (QIcon::ThemeIcon, const QIcon&)
    :digest: a951f85ad60de37a66c31df15605ccc4

Returns the :sip:ref:`~PyQt6.QtGui.QIcon` corresponding to *icon* in the :sip:ref:`~PyQt6.QtGui.QIcon.themeName`.

If the current theme does not provide an icon for *icon*, the :sip:ref:`~PyQt6.QtGui.QIcon.fallbackThemeName` is consulted, before falling back to looking up standalone icon files in the :sip:ref:`~PyQt6.QtGui.QIcon.fallbackSearchPaths`. Finally, the platform's native icon library is consulted.

If no icon is found and a *fallback* is provided, *fallback* is returned. This is useful to provide a guaranteed fallback, regardless of whether the current set of icon themes and fallbacks paths support the requested icon.

If no icon is found and no *fallback* is provided, a default constructed, empty :sip:ref:`~PyQt6.QtGui.QIcon` is returned.
