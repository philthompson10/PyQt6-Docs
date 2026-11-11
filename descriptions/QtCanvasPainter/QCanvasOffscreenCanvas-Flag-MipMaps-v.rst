.. sip:enum-member-description::
    :status: todo
    :value: 0x02
    :digest: 300fb8d0d3154f1ad793b1a6d9ae771d

Indicates that the canvas' backing texture should have mipmapping enabled. Setting this flag is not supported when the sample count is greater than 1. Note that the mipmap sequence is generated when calling :sip:ref:`~PyQt6.QtCanvasPainter.QCanvasPainter.addImage` with the :sip:ref:`~PyQt6.QtCanvasPainter.QCanvasPainter.ImageFlag.GenerateMipmaps` flag set. This implies that addImage() must be called every time after the canvas' content changes, so that the mipmap chain is regenerated. Frequent mipmap generation can have a negative effect on performance.
