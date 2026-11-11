.. sip:method-description::
    :status: todo
    :pysig: 7744369b480bfd8db6e31c73ca56d272
    :realsig: () const
    :digest: d58077070c019596ed15edae80912e68

Returns the tessellation execution mode for a tessellation control or evaluation shader.

When not set, the returned value is :sip:ref:`~PyQt6.QtGui.QShaderDescription.TessellationMode.UnknownTessellationMode`.

For example, for a tessellation evaluation shader with the following declaration the function returns :sip:ref:`~PyQt6.QtGui.QShaderDescription.TessellationMode.TrianglesTessellationMode`.

::

    layout(triangles) in;
