.. sip:method-description::
    :status: todo
    :pysig: eacd67dd9e023b7df0e7377d131fff1c
    :realsig: (QRhiTexture::NativeTexture)
    :digest: 7a794857e242371a9f7a995d1ad0d5db

Similar to create(), except that no new native textures are created. Instead, the native texture resources specified by *src* is used.

This allows importing an existing native texture object (which must belong to the same device or sharing context, depending on the graphics API) from an external graphics engine.

Returns true if the specified existing native texture object has been successfully wrapped as a non-owning :sip:ref:`~PyQt6.QtGui.QRhiTexture`.

**Note:** format(), pixelSize(), sampleCount(), and flags() must still be set correctly. Passing incorrect sizes and other values to :sip:ref:`~PyQt6.QtGui.QRhi.newTexture` and then following it with a createFrom() expecting that the native texture object alone is sufficient to deduce such values is **wrong** and will lead to problems.

**Note:** :sip:ref:`~PyQt6.QtGui.QRhiTexture` does not take ownership of the texture object. destroy() does not free the object or any associated memory.

The opposite of this operation, exposing a :sip:ref:`~PyQt6.QtGui.QRhiTexture`-created native texture object to a foreign engine, is possible via :sip:ref:`~PyQt6.QtGui.QRhiTexture.nativeTexture`.

**Note:** When importing a 3D texture, or a texture array object, or, with OpenGL ES, an external texture, it is then especially important to set the corresponding flags (\ :sip:ref:`~PyQt6.QtGui.QRhiTexture.Flag.ThreeDimensional`, :sip:ref:`~PyQt6.QtGui.QRhiTexture.Flag.TextureArray`, :sip:ref:`~PyQt6.QtGui.QRhiTexture.Flag.ExternalOES`) via setFlags() before calling this function.
