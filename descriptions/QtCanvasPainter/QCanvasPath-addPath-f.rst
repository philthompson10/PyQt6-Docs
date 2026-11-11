.. sip:method-description::
    :status: todo
    :pysig: 042905aa76e8d3bc3a57cd84da6a505d
    :realsig: (const QCanvasPath&, const QTransform&)
    :digest: c1146e4758e6a1522ec788dbc2d6d95c

Adds *path* into this path, optionally using *transform* to alter the path points. When *transform* is not provided (or it is identity matrix), this operation is very fast as it reuses the path data.
