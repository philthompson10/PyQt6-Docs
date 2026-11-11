.. sip:enum-member-description::
    :status: todo
    :value: 3
    :digest: 7f90314d79babf867e059c0ea73a9ae0

A vertex shader meant to be used in a Metal pipeline with tessellation in combination with indexed draw calls sourcing index data from a uint32 index buffer. To support the Metal tessellation pipeline, the vertex shader is translated to a compute shader that may be dependent on the index buffer usage in the draw calls (e.g. if the shader is using gl_VertexIndex), hence the need for three dedicated variants.
