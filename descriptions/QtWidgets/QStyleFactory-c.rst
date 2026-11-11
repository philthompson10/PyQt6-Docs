.. sip:class-description::
    :status: todo
    :brief: Creates QStyle objects
    :digest: fba7e03d635dd60e656c31b8a8b15fcd

The :sip:ref:`~PyQt6.QtWidgets.QStyleFactory` class creates :sip:ref:`~PyQt6.QtWidgets.QStyle` objects.

The :sip:ref:`~PyQt6.QtWidgets.QStyle` class is an abstract base class that encapsulates the look and feel of a GUI. :sip:ref:`~PyQt6.QtWidgets.QStyleFactory` creates a :sip:ref:`~PyQt6.QtWidgets.QStyle` object using the :sip:ref:`~PyQt6.QtWidgets.QStyleFactory.create` function and a key identifying the style. The styles are either built-in or dynamically loaded from a style plugin (see QStylePlugin).

Use the :sip:ref:`~PyQt6.QtWidgets.QStyleFactory.keys` function to retrieve the valid keys. The built-in styles, typically "windows" and "fusion", are always available. The platform styles are plugins and are available on their platform only: "windows11", which follows the Windows 11 Fluent design, and "windowsvista" on Windows, "macos" on macOS, and "android" on Android. The keys are case-insensitive.

.. seealso:: :sip:ref:`~PyQt6.QtWidgets.QStyle`.
