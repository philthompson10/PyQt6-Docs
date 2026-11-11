.. sip:method-description::
    :status: todo
    :pysig: 19a442afe84fca1345cc7ae4ce9a0264
    :realsig: (QAnyStringView, QAnyStringView, QObject*)
    :digest: 5b5af650b1637ad97610155613454c51

Set the singleton instance to use for the given type on the QML engine.

This function allows you to manually set a :sip:ref:`~PyQt6.QtCore.QObject`-derived instance to use as the singleton in QML for this engine. This allows you to control the creation of the instance. This can be useful in several scenarios, including for cases where your singleton needs to communicate with backend components.

This function takes the *moduleName* and *typeName* to indicate the singleton type you are trying to set, and the *instance* to set. The type has to be already registered as a QML singleton type, ideally by using QML_ELEMENT and `QML_SINGLETON <https://doc.qt.io/qt-6/qtqml-documents-structure.html#singleton>`_. If the module has not already been loaded, it will be now.

The function returns true on success or false on failure. If a failure occurs, a warning is emitted detailing the failure.

As an example, the singleton might need a backend service to work, and could then be declared as follows:

.. literalinclude:: ../../../snippets/qtdeclarative-src-qml-doc-snippets-code-src_qml_qqmlengine.py

Upon initialization of the application, you can then do:

.. literalinclude:: ../../../snippets/qtdeclarative-src-qml-doc-snippets-code-src_qml_qqmlengine.py

Note instead of providing a default constructor or a static create function, the QML_UNCREATABLE() macro was used to indicate this item cannot be created by the qml engine.

Singleton instances can only be set once per type and engine, and must be set before any use. Once a singleton instance is created or set, it is no longer possible to set it using this function, so you should set the instances before they are first used from QML.

The engine will *not* take ownership of the instance you pass, unless you explicitly instruct the engine to do so by using :sip:ref:`~PyQt6.QtQml.QJSEngine.setObjectOwnership`.

**Warning:** Make sure the *instance* outlives the lifetime of the engine.
