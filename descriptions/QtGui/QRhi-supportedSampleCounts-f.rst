.. sip:method-description::
    :status: todo
    :pysig: 2e0b8f22613494b44c9678f7b212141a
    :realsig: () const
    :digest: 019df0b2109fd0ed70ac942ea65c12f1

Returns the list of supported sample counts.

A typical example would be (1, 2, 4, 8).

With some backend this list of supported values is fixed in advance, while with some others the (physical) device properties indicate what is supported at run time.

.. seealso:: QRhiRenderBuffer::setSampleCount()QRhiTexture::setSampleCount()QRhiGraphicsPipeline::setSampleCount()QRhiSwapChain::setSampleCount().
