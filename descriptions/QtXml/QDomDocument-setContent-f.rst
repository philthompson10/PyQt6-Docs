.. sip:method-description::
    :status: todo
    :pysig: 716309d2c154766d5aad494d63606333
    :realsig: (QXmlStreamReader*, QDomDocument::ParseOptions)
    :digest: c3a03329386b4505d80559bd8ffc9f1e

This function parses the XML document from the byte array *data*, string view *text*, IO *device*, or stream *reader* and sets it as the content of the document. It tries to detect the encoding of the document, in accordance with the XML specification. Returns the result of parsing in ParseResult, which explicitly converts to ``bool``.

You can use the *options* parameter to specify different parsing options, for example, to enable namespace processing, etc.

By default, namespace processing is disabled. If it's disabled, the parser does no namespace processing when it reads the XML file. The functions :sip:ref:`~PyQt6.QtXml.QDomNode.prefix`, :sip:ref:`~PyQt6.QtXml.QDomNode.localName` and :sip:ref:`~PyQt6.QtXml.QDomNode.namespaceURI` return an empty string.

If namespace processing is enabled via the parse *options*, the parser recognizes namespaces in the XML file and sets the prefix name, local name and namespace URI to appropriate values. The functions :sip:ref:`~PyQt6.QtXml.QDomNode.prefix`, :sip:ref:`~PyQt6.QtXml.QDomNode.localName` and :sip:ref:`~PyQt6.QtXml.QDomNode.namespaceURI` return a string for all elements and attributes and return an empty string if the element or attribute has no prefix.

Text nodes consisting only of whitespace are stripped and won't appear in the :sip:ref:`~PyQt6.QtXml.QDomDocument`. Since Qt 6.5, one can pass :sip:ref:`~PyQt6.QtXml.QDomDocument.ParseOption.PreserveSpacingOnlyNodes` as a parse option, to specify that spacing-only text nodes must be preserved.

Entity references are handled as follows:

* References to internal general entities and character entities occurring in the content are included. The result is a :sip:ref:`~PyQt6.QtXml.QDomText` node with the references replaced by their corresponding entity values.

* References to parameter entities occurring in the internal subset are included. The result is a :sip:ref:`~PyQt6.QtXml.QDomDocumentType` node which contains entity and notation declarations with the references replaced by their corresponding entity values.

* Any general parsed entity reference which is not defined in the internal subset and which occurs in the content is represented as a :sip:ref:`~PyQt6.QtXml.QDomEntityReference` node.

* Any parsed entity reference which is not defined in the internal subset and which occurs outside of the content is replaced with an empty string.

* Any unparsed entity reference is replaced with an empty string.

**Note:** The overload taking IO *device* will try to open it in read-only mode if it is not already open. In that case, the caller is responsible for calling close. This will change in Qt 7, which will no longer open the IO *device*. Applications should therefore open the device themselves before calling :sip:ref:`~PyQt6.QtXml.QDomDocument.setContent`.

.. seealso:: ParseResult, ParseOptions.
