.. sip:method-description::
    :status: todo
    :pysig: d41d8cd98f00b204e9800998ecf8427e
    :realsig: ()
    :digest: 36a665e71233f52c306c0fd5eec11537

Stops processing audio data, preserving buffered audio data.

Sets :sip:ref:`~PyQt6.QtMultimedia.QAudioSink.state` to QtAudio::SuspendedState and emits :sip:ref:`~PyQt6.QtMultimedia.QAudioSink.stateChanged` signal.
