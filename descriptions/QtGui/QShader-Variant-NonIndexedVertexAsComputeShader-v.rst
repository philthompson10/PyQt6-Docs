.. sip:enum-member-description::
    :status: todo
    :value: 4
    :digest: 3c7ecb2a3a900bc6b9a9738c3bf7f6aa

A vertex shader meant to be used in a Metal pipeline with tessellation in combination with non-indexed draw calls. To support the Metal tessellation pipeline, the vertex shader is translated to a compute shader that may be dependent on the index buffer usage in the draw calls (e.g. if the shader is using gl_VertexIndex), hence the need for three dedicated variants.
