.. sip:method-description::
    :status: todo
    :pysig: d41d8cd98f00b204e9800998ecf8427e
    :realsig: ()
    :digest: 30efe44887adea12e4e54830d0ece2dc

Constructs a spatial audio engine with *parent*, if any.

The engine will operate with a sample rate given by *sampleRate*. The default sample rate, if none is provided, is 44100 (44.1kHz).

Sound content that is not provided at that sample rate will automatically get resampled to *sampleRate* when being processed by the engine. The default sample rate is fine in most cases, but you can define a different rate if most of your sound files are sampled with a different rate, and avoid some CPU overhead for resampling.
