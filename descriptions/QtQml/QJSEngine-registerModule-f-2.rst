.. sip:method-description::
    :status: todo
    :pysig: c84e167efe5d0094896fb92f14a761b7
    :realsig: (const QString&, const QJSValue&)
    :digest: 2e6f21a445a7b62903f70c9add9b5311

Registers a :sip:ref:`~PyQt6.QtQml.QJSValue` to serve as a module. After this function is called, all modules that import *moduleName* will import the value of *value* instead of loading *moduleName* from the filesystem.

Any valid :sip:ref:`~PyQt6.QtQml.QJSValue` can be registered, but named exports (i.e. ``import { name } from "info"``) are treated as members of an object, so the default export must be created with one of the newXYZ methods of :sip:ref:`~PyQt6.QtQml.QJSEngine`.

Because this allows modules that do not exist on the filesystem to be imported, scripting applications can use this to provide built-in modules, similar to Node.js.

Returns ``true`` on success, ``false`` otherwise.

**Note:** The :sip:ref:`~PyQt6.QtQml.QJSValue` *value* is not called or read until it is used by another module. This means that there is no code to evaluate, so no errors will be seen until another module throws an exception while trying to load this module.

**Warning:** Attempting to access a named export from a :sip:ref:`~PyQt6.QtQml.QJSValue` that is not an object will trigger a :ref:`qjsengine-script-exceptions`.

**Warning:** When a module is registered, the engine evaluates and snapshots the properties of *value* to determine what will be exported. For a wrapped :sip:ref:`~PyQt6.QtCore.QObject`, this means its properties are only read once, and subsequent modifications to those properties will *not* be reflected when accessed from JavaScript. If your :sip:ref:`~PyQt6.QtCore.QObject` has properties whose values change after module registration, do not register the :sip:ref:`~PyQt6.QtCore.QObject` directly. Instead, wrap it inside another object:

::

    // C++ setup
    QJSValue container = engine.newObject();
    container.setProperty("instance", engine.newQObject(&myDynamicObject));
    engine.registerModule("api.mjs", container);

    // JavaScript usage
    import {instance as Api} from "api.mjs"

    // ...

    console.log(Api.dynamicProperty)

.. seealso:: :sip:ref:`~PyQt6.QtQml.QJSEngine.importModule`.
