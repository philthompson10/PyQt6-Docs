.. sip:enum-member-description::
    :status: todo
    :value: 0x0001
    :digest: dad585e6b8757b876daa96072a4f1f8d

The file is executable by others.

**Warning:** Because of differences in the platforms supported by Qt, the semantics of ReadUser, WriteUser and ExeUser are platform-dependent: On Unix, the rights of the owner of the file are returned and on Windows the rights of the current user are returned. This behavior might change in a future Qt version.

**Note:** On NTFS file systems, ownership and permissions checking is disabled by default for performance reasons. To enable it, include the following line:

.. literalinclude:: ../../../snippets/qtbase-src-corelib-doc-snippets-ntfsp.py
    :lines: 55-55
