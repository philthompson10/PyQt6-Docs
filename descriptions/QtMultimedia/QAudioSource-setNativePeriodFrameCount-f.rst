.. sip:method-description::
    :status: todo
    :pysig: fa7153f7ed1cb6c0fcf2ffb2fac21748
    :realsig: (qsizetype)
    :digest: ff2fd788f74062fc70682211002807af

Sets the native period frame count to *frameCount*.

Tunes the audio buffer size used by the operating system and hardware. By default (when not set), the system uses a platform-dependent value, typically 1024 frames (~23ms at 44100 Hz).

Use smaller values (64-256) to reduce latency, or larger values (2048-4096) to reduce the risk of buffer overruns (dropouts).

Valid values are powers of 2 between 32 and 4096 (inclusive), or -1 to unset. Can only be called when the audio source is stopped.

Maps to platform-specific settings: ``kAudioDevicePropertyBufferFrameSize`` (macOS), ``IAudioClient::bufferDuration`` (Windows), ``PW_KEY_NODE_FORCE_QUANTUM`` (PipeWire/Linux), and ``AAudioStreamBuilder_setBufferCapacityInFrames`` (Android).

**Note:** This is separate from the ringbuffer configured with :sip:ref:`~PyQt6.QtMultimedia.QAudioSource.setBufferSize` or :sip:ref:`~PyQt6.QtMultimedia.QAudioSource.setBufferFrameCount`.

.. seealso:: :sip:ref:`~PyQt6.QtMultimedia.QAudioSource.nativePeriodFrameCount`.
