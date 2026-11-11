.. sip:method-description::
    :status: todo
    :pysig: fa7153f7ed1cb6c0fcf2ffb2fac21748
    :realsig: (qsizetype)
    :digest: 5313751c14b90d0fbfcfd15f42c3feaa

Sets the audio buffer size to *value* in frame count.

**Note:** This function can be called anytime before :sip:ref:`~PyQt6.QtMultimedia.QAudioSink.start`. Calls to this are ignored after :sip:ref:`~PyQt6.QtMultimedia.QAudioSink.start`. It should not be assumed that the buffer size set is the actual buffer size used - call :sip:ref:`~PyQt6.QtMultimedia.QAudioSink.bufferFrameCount` anytime after :sip:ref:`~PyQt6.QtMultimedia.QAudioSink.start` to return the actual buffer size being used.

The :sip:ref:`~PyQt6.QtMultimedia.QAudioSink.bufferFrameCount` and :sip:ref:`~PyQt6.QtMultimedia.QAudioSink.bufferSize` properties denote the ringbuffer size when using the :sip:ref:`~PyQt6.QtCore.QIODevice` APIs. The native period size is controlled via :sip:ref:`~PyQt6.QtMultimedia.QAudioSink.setNativePeriodFrameCount`.

.. seealso:: :sip:ref:`~PyQt6.QtMultimedia.QAudioSink.bufferFrameCount`, :sip:ref:`~PyQt6.QtMultimedia.QAudioSink.setBufferSize`.
