.. sip:method-description::
    :status: todo
    :pysig: e245c21eefbef66f37cf5437c5250b45
    :realsig: () const
    :digest: 5f679179d050b704b86d4debb5e81037

Returns the tessellation winding order for a tessellation control or evaluation shader.

When not set, the returned value is :sip:ref:`~PyQt6.QtGui.QShaderDescription.TessellationWindingOrder.UnknownTessellationWindingOrder`.

For example, for a tessellation evaluation shader with the following declaration the function returns :sip:ref:`~PyQt6.QtGui.QShaderDescription.TessellationWindingOrder.CcwTessellationWindingOrder`.

::

    layout(triangles, fractional_odd_spacing, ccw) in;
