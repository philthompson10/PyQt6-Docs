.. sip:method-description::
    :status: todo
    :pysig: 331a08080299e338babf986691739129
    :realsig: (const QString&, quint32)
    :digest: 89ea629dce7c9823c137028e7288ac5f

Runs the JavaScript code contained in *script* on this frame, without checking whether the DOM of the page has been constructed. To avoid conflicts with other scripts executed on the page, the world in which the script is run is specified by *worldId*. The world ID values are the same as provided by :sip:ref:`~PyQt6.QtWebEngineCore.QWebEngineScript.ScriptWorldId`, and between ``0`` and ``256``. If you leave out the ``world`` ID, the script is run in the ``MainWorld``. When the script has been executed, *callback* is called with the result of the last executed statement. ``callback`` can be any of a function pointer, a functor or a lambda, and it is expected to take a :sip:ref:`~PyQt6.QtCore.QVariant` parameter. For example:

::

    page.runJavaScript("document.title", [](const QVariant &v) { qDebug() << v.toString(); });

Only plain data can be returned from JavaScript as the result value. Supported data types include all of the JSON data types as well as, for example, ``Date`` and ``ArrayBuffer``. Unsupported data types include, for example, ``Function`` and ``Promise``.

**Note:** In Qt versions prior to 6.12, the callback had to be copyable.

**Warning:** Do not execute lengthy routines in the callback function, because it might block the rendering of the web engine page.

**Warning:** We guarantee that the *callback* is always called, but it might be done during page destruction. When :sip:ref:`~PyQt6.QtWebEngineCore.QWebEnginePage` is deleted, the callback is triggered with an invalid value and it is not safe to use the corresponding :sip:ref:`~PyQt6.QtWebEngineCore.QWebEnginePage` or :sip:ref:`~PyQt6.QtWebEngineWidgets.QWebEngineView` instance inside it.

.. seealso:: :sip:ref:`~PyQt6.QtWebEngineCore.QWebEngineScript.ScriptWorldId`, :sip:ref:`~PyQt6.QtWebEngineCore.QWebEnginePage.runJavaScript`, `Script Injection <https://doc.qt.io/qt-6/qtwebengine-overview.html#script-injection>`_.
