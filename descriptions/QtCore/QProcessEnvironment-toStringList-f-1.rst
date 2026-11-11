.. sip:method-description::
    :status: todo
    :pysig: 3c9a938a1e983dbe538fd869f2db5e67
    :realsig: () const
    :digest: 1bd278dc239903952497e9ab95282cb7

Converts this :sip:ref:`~PyQt6.QtCore.QProcessEnvironment` object into a list of strings, one for each environment variable that is set. The environment variable's name and its value are separated by an equal character ('=').

The QStringList contents returned by this function are suitable for presentation. Use with the QProcess::setEnvironment function is not recommended due to potential encoding problems under Unix, and worse performance.

.. seealso:: :sip:ref:`~PyQt6.QtCore.QProcessEnvironment.systemEnvironment`, :sip:ref:`~PyQt6.QtCore.QProcess.systemEnvironment`, :sip:ref:`~PyQt6.QtCore.QProcess.setProcessEnvironment`.
