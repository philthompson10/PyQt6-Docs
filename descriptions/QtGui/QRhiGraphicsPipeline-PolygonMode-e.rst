.. sip:enum-description::
    :status: todo
    :digest: 0162c16086f6f0744266a3255d125d0f

Specifies the polygon rasterization mode

Polygon Mode (Triangle Fill Mode in Metal, Fill Mode in D3D) specifies the fill mode used when rasterizing polygons. Polygons may be drawn as solids (Fill), or as a wire mesh (Line).

Support for non-fill polygon modes is optional and is indicated by the :sip:ref:`~PyQt6.QtGui.QRhi.Feature.NonFillPolygonMode` feature. With OpenGL ES and some Vulkan implementations the feature will likely be reported as unsupported, which then means values other than Fill cannot be used.
