.. sip:class-description::
    :status: todo
    :brief: Holds the environment variables that can be passed to a program
    :digest: f1b749380b45965edd27bf381d5c2769

The :sip:ref:`~PyQt6.QtCore.QProcessEnvironment` class holds the environment variables that can be passed to a program.

A process's environment is composed of a set of key=value pairs known as environment variables. The :sip:ref:`~PyQt6.QtCore.QProcessEnvironment` class wraps that concept and allows easy manipulation of those variables. It's meant to be used along with :sip:ref:`~PyQt6.QtCore.QProcess`, to set the environment for child processes. It cannot be used to change the current process's environment.

The environment of the calling process can be obtained using :sip:ref:`~PyQt6.QtCore.QProcessEnvironment.systemEnvironment`.

On Unix systems, the variable names are case-sensitive. Note that the Unix environment allows both variable names and contents to contain arbitrary binary data (except for the NUL character). :sip:ref:`~PyQt6.QtCore.QProcessEnvironment` will preserve such variables, but does not support manipulating variables whose names or values cannot be encoded by the current locale settings (see QString::toLocal8Bit).

On Windows, the variable names are case-insensitive, but case-preserving. :sip:ref:`~PyQt6.QtCore.QProcessEnvironment` behaves accordingly.

.. _qprocessenvironment-security-considerations:

Security Considerations
-----------------------

Extending a process environment with new environment variables or adjusting ``PATH`` may expose the system to security vulnerabilities, for example via executing an untrusted binary. Therefore it is recommended to validate all user input before passing it to the process environment.

.. seealso:: :sip:ref:`~PyQt6.QtCore.QProcess`, :sip:ref:`~PyQt6.QtCore.QProcess.systemEnvironment`, :sip:ref:`~PyQt6.QtCore.QProcess.setProcessEnvironment`.
