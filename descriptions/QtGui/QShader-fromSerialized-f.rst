.. sip:method-description::
    :status: todo
    :pysig: ecb853001bf9d7995b9c78dd428adaf8
    :realsig: (const QByteArray&)
    :digest: e75a13afd8f9f8ee5ba790e22816e4bb

Creates a new :sip:ref:`~PyQt6.QtGui.QShader` instance from the given *data*.

If *data* cannot be deserialized successfully, the result is a default constructed :sip:ref:`~PyQt6.QtGui.QShader` for which :sip:ref:`~PyQt6.QtGui.QShader.isValid` returns ``false``.

**Warning:** Shader packages, including ``.qsb`` files in the filesystem, are assumed to be trusted content. Application developers are advised to carefully consider the potential implications before allowing the loading of user-provided content that is not part of the application.

.. seealso:: :sip:ref:`~PyQt6.QtGui.QShader.serialized`.
