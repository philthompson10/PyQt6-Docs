.. sip:class-description::
    :status: todo
    :brief: Allows applications to access Chrome/Firefox extension-compatible interfaces through managed packages
    :digest: 0e41e92c57394bc377d2ea31ba261458

The :sip:ref:`~PyQt6.QtWebEngineCore.QWebEngineExtensionManager` class allows applications to access Chrome/Firefox extension-compatible interfaces through managed packages.

:sip:ref:`~PyQt6.QtWebEngineCore.QWebEngineExtensionManager` exposes interfaces compatible with the Chrome/Firefox extension platform, letting applications load or install packages built against that format at runtime.

Loading via :sip:ref:`~PyQt6.QtWebEngineCore.QWebEngineExtensionManager.loadExtension` is temporary and doesn't persist across sessions, while :sip:ref:`~PyQt6.QtWebEngineCore.QWebEngineExtensionManager.installExtension` stores the package in the profile directory so it loads automatically at startup.

Loaded packages can be inspected through :sip:ref:`~PyQt6.QtWebEngineCore.QWebEngineExtensionManager.extensions` property, which returns a list of :sip:ref:`~PyQt6.QtWebEngineCore.QWebEngineExtensionInfo` objects, and the manager emits signals when packages are loaded, installed, unloaded, or uninstalled. The :sip:ref:`~PyQt6.QtWebEngineCore.QWebEngineExtensionManager.installPath` property indicates where installed packages are persisted.

Only the ManifestV3 specification is supported — packages using other manifest versions are rejected outright. This capability is not available for off-the-record profiles. Every profile ships with two built-in components, Google Hangouts and the Chromium PDF Viewer, which can be disabled if not needed.

**Note:** If you use this API to develop a system that allows users to install extensions at runtime, you may fall under the CRA EN-304-617 rules on browser extensions.

.. seealso:: :sip:ref:`~PyQt6.QtWebEngineCore.QWebEngineProfile.extensionManager`, :sip:ref:`~PyQt6.QtWebEngineCore.QWebEngineExtensionInfo`.
