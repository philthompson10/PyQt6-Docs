.. sip:method-description::
    :status: todo
    :pysig: d41d8cd98f00b204e9800998ecf8427e
    :realsig: ()
    :digest: cb5cf258f583c968e8db4e8f5a4a216c

Resumes processing audio data after a :sip:ref:`~PyQt6.QtMultimedia.QAudioSource.suspend`.

Sets :sip:ref:`~PyQt6.QtMultimedia.QAudioSource.state` to the state the sink had when :sip:ref:`~PyQt6.QtMultimedia.QAudioSource.suspend` was called. This function does nothing if the audio sink's state is not QtAudio::SuspendedState.
