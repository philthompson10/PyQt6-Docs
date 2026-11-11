.. sip:class-description::
    :status: todo
    :brief: Entity resolver for a QXmlStreamReader
    :digest: 9c5370deacb15a4ab68ea7c20b4c4511

The :sip:ref:`~PyQt6.QtCore.QXmlStreamEntityResolver` class provides an entity resolver for a :sip:ref:`~PyQt6.QtCore.QXmlStreamReader`.

Use to inform :sip:ref:`~PyQt6.QtCore.QXmlStreamReader` how to expand entities not :sip:ref:`~PyQt6.QtCore.QXmlStreamReader.entityDeclarations`.

.. _qxmlstreamentityresolver-sec-con-qxmlstreamentityresolver:

.. _qxmlstreamentityresolver-security-considerations:

Security Considerations
-----------------------

.. _qxmlstreamentityresolver-sec-con-qxmlstreamentityresolver-cycles:

.. _qxmlstreamentityresolver-entity-cycles:

Entity Cycles
.............

You must take care to avoid resolving entities in cycles, because :sip:ref:`~PyQt6.QtCore.QXmlStreamReader` only detects and rejects cycles in :sip:ref:`~PyQt6.QtCore.QXmlStreamReader.entityDeclarations`, not in entities expanded from an implementation of the :sip:ref:`~PyQt6.QtCore.QXmlStreamEntityResolver` interface.

This is by design: :sip:ref:`~PyQt6.QtCore.QXmlStreamReader` puts the work on the implementation of a concrete :sip:ref:`~PyQt6.QtCore.QXmlStreamEntityResolver`. For static mappings, like `XML Entity Definitions for Characters <https://www.w3.org/TR/xml-entity-names/>`_, this is trivially guaranteed, so running some tracking in the background would just slow things down for everyone.

Things get interesting when you read entity definitions from external input, including untrusted sources. In this case, *your implementation* must ensure the expansions it uses as input are cycle-free. This is a `simple graph operation <https://en.wikipedia.org/wiki/Cycle_(graph_theory)#Cycle_detection>`_ that can be implemented in linear time and space and can be performed up front at load time, so it doesn't affect :sip:ref:`~PyQt6.QtCore.QXmlStreamEntityResolver.resolveUndeclaredEntity` performance.

.. _qxmlstreamentityresolver-sec-con-qxmlstreamentityresolver-expansion-limit:

.. _qxmlstreamentityresolver-entity-expansion-limit:

Entity Expansion Limit
......................

At the moment, entities resolved by this class do not count against :sip:ref:`~PyQt6.QtCore.QXmlStreamReader.entityExpansionLimit`. This may change in future versions of Qt.

For the time being, you need to enforce some upper expansion limit yourself, if you read entity definitions from external input. After cycle detection, `longest-path calculation <https://en.wikipedia.org/wiki/Longest_path_problem#Acyclic_graphs>`_ is a simple graph operation that can be implemented in linear time and space and can be performed up front at load time, so it, too, doesn't affect :sip:ref:`~PyQt6.QtCore.QXmlStreamEntityResolver.resolveUndeclaredEntity` performance.

.. seealso:: :sip:ref:`~PyQt6.QtCore.QXmlStreamReader.setEntityResolver`.
