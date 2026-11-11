.. sip:method-description::
    :status: todo
    :pysig: aa18efac6778fcf348b8e9cadb69657d
    :realsig: (QRhiSampler::Filter, QRhiSampler::Filter, QRhiSampler::Filter, QRhiSampler::AddressMode, QRhiSampler::AddressMode, QRhiSampler::AddressMode)
    :digest: 43366fd85a640a37f612673b89ab33b6

Returns a new sampler with the specified magnification filter *magFilter*, minification filter *minFilter*, mipmapping mode *mipmapMode*, and the addressing (wrap) modes *addressU*, *addressV*, and *addressW*.

**Note:** Setting *mipmapMode* to a value other than ``None`` implies that images for all relevant mip levels will be provided either via :sip:ref:`~PyQt6.QtGui.QRhiResourceUpdateBatch.uploadTexture` or by calling :sip:ref:`~PyQt6.QtGui.QRhiResourceUpdateBatch.generateMips` on the texture that is used with this sampler. Attempting to use the sampler with a texture that has no data for all relevant mip levels will lead to rendering errors, with the exact behavior dependent on the underlying graphics API.

.. seealso:: :sip:ref:`~PyQt6.QtGui.QRhiResource.destroy`.
