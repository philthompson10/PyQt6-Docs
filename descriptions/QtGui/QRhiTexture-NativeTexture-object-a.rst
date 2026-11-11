.. sip:attribute-description::
    :status: todo
    :digest: 7c4297e2ba32f0cc50d2815fe488bc64

This variable holds 64-bit integer containing the native object handle..

With OpenGL, the native handle is a GLuint value, so ``object`` can then be cast to a GLuint. With Vulkan, the native handle is a VkImage, so ``object`` can be cast to a VkImage. With Direct3D 11 and Metal ``object`` contains a ID3D11Texture2D or MTLTexture pointer, respectively. With Direct3D 12 ``object`` contains a ID3D12Resource pointer.
