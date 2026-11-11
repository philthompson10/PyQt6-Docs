.. sip:method-description::
    :status: todo
    :pysig: 92edbfa69aa02cf3d0c1c72c6279097f
    :realsig: () const
    :digest: 5e339be69459cda57d94c531b65b8432

Returns the tessellation partitioning mode for a tessellation control or evaluation shader.

When not set, the returned value is :sip:ref:`~PyQt6.QtGui.QShaderDescription.TessellationPartitioning.UnknownTessellationPartitioning`.

For example, for a tessellation evaluation shader with the following declaration the function returns :sip:ref:`~PyQt6.QtGui.QShaderDescription.TessellationPartitioning.FractionalOddTessellationPartitioning`.

::

    layout(triangles, fractional_odd_spacing, ccw) in;
