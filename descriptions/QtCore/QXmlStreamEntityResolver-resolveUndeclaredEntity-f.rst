.. sip:method-description::
    :status: todo
    :pysig: 558877a2dde966820eb6e4a9d974f77b
    :realsig: (const QString&)
    :digest: e7267c4952dfa32b2198d8dad6994956

Reimplement this function to resolve the undeclared entity *name* and return its replacement text. If the entity is unknown to the entity resolver, return a null string: ``QString()``. This will raise an error in QXmlStreamreader. An empty, but non-null string is considered a valid expansion of the entity, and will not cause an error.

The default implementation always returns ``QString()``.
