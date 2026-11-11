.. sip:method-description::
    :status: todo
    :pysig: 5dc7804c293f9cf1c9d5b7d1139613f3
    :realsig: (const QJSValue&, const QJSValueList&) const
    :digest: 1b51728d8aec79e581a852c74a8880c5

If this :sip:ref:`~PyQt6.QtQml.QJSManagedValue` represents a JavaScript FunctionObject, calls it on *instance* with the given *arguments*, and returns the result. Otherwise returns a JavaScript ``undefined`` value.

The *arguments* and the *instance* have to be either primitive values or belong to the same :sip:ref:`~PyQt6.QtQml.QJSEngine` as this :sip:ref:`~PyQt6.QtQml.QJSManagedValue`. Otherwise the call is not carried out and a JavaScript ``undefined`` value is returned.
