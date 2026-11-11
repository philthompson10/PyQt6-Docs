.. sip:method-description::
    :status: todo
    :pysig: fa7153f7ed1cb6c0fcf2ffb2fac21748
    :realsig: (int)
    :digest: cbb789f568893d313d2e8c952f8003a0

Sets the maximum amount of characters a single entity is allowed to expand into to *limit*. If a single entity expands past the given limit, the document is not considered well formed.

The limit is there to prevent DoS attacks when loading unknown XML documents where recursive entity expansion could otherwise exhaust all available memory.

The default value for this property is 4096 characters.

The minimum is one (1), to support the built-in XML entities (``&lt;`` etc).

.. seealso:: :sip:ref:`~PyQt6.QtCore.QXmlStreamReader.entityExpansionLimit`.
