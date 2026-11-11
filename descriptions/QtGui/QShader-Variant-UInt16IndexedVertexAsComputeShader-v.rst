.. sip:enum-member-description::
    :status: todo
    :value: 2
    :digest: 3e88667441456ebac4c6e17e8fe4cc98

A vertex shader meant to be used in a Metal pipeline with tessellation in combination with indexed draw calls sourcing index data from a uint16 index buffer. To support the Metal tessellation pipeline, the vertex shader is translated to a compute shader that may be dependent on the index buffer usage in the draw calls (e.g. if the shader is using gl_VertexIndex), hence the need for three dedicated variants.
