.. sip:class-description::
    :status: todo
    :brief: Locking between processes using a file
    :digest: 709552b46fda98357f3d27be430d651e

The :sip:ref:`~PyQt6.QtCore.QLockFile` class provides locking between processes using a file.

A lock file can be used to prevent multiple processes from accessing concurrently the same resource. For instance, a configuration file on disk, or a socket, a port, a region of shared memory...

Serialization is only guaranteed if all processes that access the shared resource use :sip:ref:`~PyQt6.QtCore.QLockFile`, with the same file path.

:sip:ref:`~PyQt6.QtCore.QLockFile` supports two use cases: to protect a resource for a short-term operation (e.g. verifying if a configuration file has changed before saving new settings), and for long-lived protection of a resource (e.g. a document opened by a user in an editor) for an indefinite amount of time.

When protecting for a short-term operation, it is acceptable to call :sip:ref:`~PyQt6.QtCore.QLockFile.lock` and wait until any running operation finishes. When protecting a resource over a long time, however, the application should always call :sip:ref:`~PyQt6.QtCore.QLockFile.setStaleLockTime`\ (0ms) and then :sip:ref:`~PyQt6.QtCore.QLockFile.tryLock` with a short timeout, in order to warn the user that the resource is locked.

If the process holding the lock crashes, the lock file stays on disk and can prevent any other process from accessing the shared resource, ever. For this reason, :sip:ref:`~PyQt6.QtCore.QLockFile` tries to detect such a "stale" lock file, based on the process ID written into the file. To cover the situation that the process ID got reused meanwhile, the current process name is compared to the name of the process that corresponds to the process ID from the lock file. If the process names differ, the lock file is considered stale. Additionally, the last modification time of the lock file (30s by default, for the use case of a short-lived operation) is taken into account. If the lock file is found to be stale, it will be deleted.

For the use case of protecting a resource over a long time, you should therefore call :sip:ref:`~PyQt6.QtCore.QLockFile.setStaleLockTime`\ (0), and when :sip:ref:`~PyQt6.QtCore.QLockFile.tryLock` returns :sip:ref:`~PyQt6.QtCore.QLockFile.LockError.LockFailedError`, inform the user that the document is locked, possibly using :sip:ref:`~PyQt6.QtCore.QLockFile.getLockInfo` for more details.

.. _qlockfile-limitations:

Limitations
-----------

:sip:ref:`~PyQt6.QtCore.QLockFile`'s implementation is usually safe, for the majority of environments and filesystems. There are a few situations in which it can incorrectly conclude a lock file is stale when it isn't, fail to detect a stale file, or race when locking. This section documents those issues.

There are two main mitigation strategies: choosing a suitable, non-zero :sip:ref:`~PyQt6.QtCore.QLockFile.staleLockTime` and choosing a regular, local filesystem for storing lock files (such as ``/var/lock`` if running as root on Unix systems or the :sip:ref:`~PyQt6.QtCore.QStandardPaths.StandardLocation.RuntimeLocation`). That may not be possible for certain use-cases of :sip:ref:`~PyQt6.QtCore.QLockFile`, such as when using :sip:ref:`~PyQt6.QtCore.QLockFile` to indicate a file path provided by the user is being edited.

.. _qlockfile-non-persistent-machine-ids:

Non-persistent machine IDs
..........................

:sip:ref:`~PyQt6.QtCore.QLockFile` uses the machine's unique ID to differentiate a lock by the current machine and one by a process running on a different host. If the machine ID changes over time (such as on systems with ephemeral storage, which must generate a new ID at every boot), :sip:ref:`~PyQt6.QtCore.QLockFile` will be unable to detect that a lock file is stale after a reboot.

Conversely, if two different machines have colliding machine IDs (for example, a cloned system image or restoration from backups) and provide a network path to :sip:ref:`~PyQt6.QtCore.QLockFile`, the class may conclude the lock is stale when it actually is not.

.. _qlockfile-absence-of-native-locking:

Absence of native locking
.........................

:sip:ref:`~PyQt6.QtCore.QLockFile` uses operating-system specific calls to indicate to other processes and threads that the lock is alive (not stale), even past the :sip:ref:`~PyQt6.QtCore.QLockFile.staleLockTime` setting. This functionality may be absent for files on some networked or virtual filesystems (such as FUSE on Linux and macOS), when using different filesystems to access the same file if the native lock isn't carried through, or in certain environments that block the necessary system calls.

If the native locking support is absent, :sip:ref:`~PyQt6.QtCore.QLockFile` will rely solely on the existence, modification time, and contents of the lock file itself. In this case, if the process currently locking the resource keeps it past :sip:ref:`~PyQt6.QtCore.QLockFile.staleLockTime`, :sip:ref:`~PyQt6.QtCore.QLockFile` will steal the lock.

.. _qlockfile-networked-filesystems:

Networked filesystems
.....................

It is unspecified whether the native file-locking is supported in networked environments: with some implementations, it is supported for all clients accessing the filesystem; for others the local system may support locking for its own processes but will not share the locking over the network; and for yet others there is no native locking even inside one host. Moreover, it is possible that some clients participate in networked locking and some others do not, for the same file. If locking is not supported across the network, :sip:ref:`~PyQt6.QtCore.QLockFile` will observe the limitations described above for the absence of native locking.

Additionally, if the lock file contains the identification of a different host, :sip:ref:`~PyQt6.QtCore.QLockFile` will be unable to confirm the process holding a lock is still running, and will need to wait :sip:ref:`~PyQt6.QtCore.QLockFile.staleLockTime` to recover from an unclean exit.

.. _qlockfile-accessing-different-actual-files-through-the-same-path:

Accessing different actual files through the same path
......................................................

It is possible for two processes to have different views of the filesystem, causing an identical file path to be different files in the filesystem. In this case, the two :sip:ref:`~PyQt6.QtCore.QLockFile` objects will likely succeed at creating the lock, but will not be mutually exclusive. This may cause conflicts if the resource the lock file is protecting is still shared between them.

This situation is most often encountered with containers (see below), but is not exclusive to them.

.. _qlockfile-files-shared-with-containers:

Files shared with containers
............................

With some container implementations, it is possible to hide the existence of some processes (for example, Linux's "PID namespace" feature). If a process is running inside of such a container but shares the machine ID of the host system or another container, two processes in different containers (or the host) will make incorrect determinations on whether the locking process is still running. Moreover, some container controllers may replace the boot ID inside of the container, causing the launched processes to conclude the lock file is always stale, regardless of how fresh its timestamp is.

With some other implementations, containers may have ephemeral storage or intentionally create a new machine ID to avoid collision. In this case, the application will experience the problems described above for non-persistent machine IDs.

However, the native file-locking usually works (subject to filesystem and environment limitations as discussed above), so even if :sip:ref:`~PyQt6.QtCore.QLockFile` did conclude the file is apparently stale, it won't steal a lock file that is natively locked.

.. _qlockfile-accesses-not-using-the-same-protocol:

Accesses not using the same protocol
....................................

:sip:ref:`~PyQt6.QtCore.QLockFile` cannot interoperate with modifications to the lock file performed outside of the protocol implemented by this class. This includes removal of the lock file by other tools, such as tmpwatch and similar, but also some virus-scanning or similar tools.

.. _qlockfile-clock-skew:

Clock skew
..........

:sip:ref:`~PyQt6.QtCore.QLockFile` relies on the time stamp of the lock file being accurate. If the clock jumps forward, :sip:ref:`~PyQt6.QtCore.QLockFile` may conclude a lock file has become stale when it hasn't, and vice-versa for jumping backwards.

For this reason, it is recommended all systems keep network-synchronized time and perform this synchronization early in their boot process. This is particularly important for networked filesystems.
