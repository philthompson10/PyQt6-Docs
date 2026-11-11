.. sip:method-description::
    :status: todo
    :pysig: 1adcf28f184055235601ceb87ae7ffd7
    :realsig: ()
    :digest: 9eda336c4053ffa9eccbbb85f6d720ea

Returns a pointer to the application's :sip:ref:`~PyQt6.QtCore.QCoreApplication` (or :sip:ref:`~PyQt6.QtGui.QGuiApplication`/\ :sip:ref:`~PyQt6.QtWidgets.QApplication`) instance.

If no instance has been allocated, ``nullptr`` is returned.

**Data race notice**: this function should not be used to test for the existence of the :sip:ref:`~PyQt6.QtCore.QCoreApplication` instance from auxiliary threads, unless the caller code is compiled as C++20.
