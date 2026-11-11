.. sip:method-description::
    :status: todo
    :pysig: 39ddd649b3552036bfe76893e4c85286
    :realsig: (QRhiTexture*, const QImage&)
    :digest: c2588b1466172aff1365c4e2c788cd9c

Enqueues uploading the image data for mip level 0 of layer 0 of the texture *tex*.

*tex* must have an uncompressed format. Its format must also be compatible with the QImage::format() of *image*. The source data is given in *image*.
