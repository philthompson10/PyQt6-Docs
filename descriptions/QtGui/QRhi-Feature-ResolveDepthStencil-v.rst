.. sip:enum-member-description::
    :status: todo
    :value: 43
    :digest: 18424ca41d0ede1816a2fb87a1647599

Indicates that resolving a multisample depth or depth-stencil texture is supported. Otherwise, setting a depth resolve texture is not functional and must be avoided. Direct 3D 11 and 12 have no support for resolving depth/depth-stencil formats, and therefore this feature will never be supported with those. Vulkan 1.0 has no API to request resolving a depth-stencil attachment. Therefore, with Vulkan this feature will only be supported with Vulkan 1.2 and up, and on 1.1 implementations with the appropriate extensions present. This feature is provided for the rare case when resolving into a non-multisample depth texture becomes necessary, for example when rendering into an OpenXR-provided depth texture (XR_KHR_composition_layer_depth). This enum value has been introduced in Qt 6.8.
