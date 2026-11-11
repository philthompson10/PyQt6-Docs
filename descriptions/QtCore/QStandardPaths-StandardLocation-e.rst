.. sip:enum-description::
    :status: todo
    :digest: 533852581011cfeb64eacc0c7b268eb2

This enum describes the different locations that can be queried using methods such as :sip:ref:`~PyQt6.QtCore.QStandardPaths.writableLocation`, :sip:ref:`~PyQt6.QtCore.QStandardPaths.standardLocations`, and :sip:ref:`~PyQt6.QtCore.QStandardPaths.displayName`.

:sip:ref:`~PyQt6.QtCore.QStandardPaths` describes each location along two independent axes: app scope (private to the calling application or shared between applications) and user scope (rooted in the calling user's directories or system-wide). Each enum value below indicates its app scope; the platform tables further down show its user scope.

Data interchange with other users is out of the scope of :sip:ref:`~PyQt6.QtCore.QStandardPaths`.

App scope
.........

A location is either *application-specific* (private to the calling application) or *generic* (shared between applications run by the same user). Application-specific locations should be assumed to be unreachable by other applications, even when run by the same user.

Sandboxed applications
^^^^^^^^^^^^^^^^^^^^^^

For sandboxed applications, on platforms such as iOS, Android, or macOS, even generic locations can be rooted in the application's sandbox container (``<APPROOT>`` in the tables below). In practice this collapses the app-scope distinction, with every location becoming effectively application-specific, and the user's system-wide shared directories reachable only through system-provided pickers, for example, :sip:ref:`~PyQt6.QtWidgets.QFileDialog`.

User scope
..........

A location is either *user-local* (rooted in the calling user's home or per-user directories) or *system-wide* (populated by the OS or by package managers, shared across users, and usually read-only to applications).

Querying :sip:ref:`~PyQt6.QtCore.QStandardPaths.writableLocation` returns the directory where files should be written, which is typically user-scoped. For application-specific locations it is also scoped to the calling application.

Querying :sip:ref:`~PyQt6.QtCore.QStandardPaths.standardLocations` returns the writable path first (if it can be determined), followed by zero or more additional locations, including both user-local and system-wide fallbacks. The additional locations are used by :sip:ref:`~PyQt6.QtCore.QStandardPaths.locate` and :sip:ref:`~PyQt6.QtCore.QStandardPaths.locateAll` to find existing files.

Sandboxed applications
^^^^^^^^^^^^^^^^^^^^^^

For sandboxed applications, system-wide locations typically fall outside the application's sandbox container, and may not exist from the application's point of view, let alone be readable or writable. They are still listed in the platform tables below for symmetry with the non-sandboxed case, and to cover applications that have been granted access through entitlements or user-driven pickers. Callers should not assume that every entry returned by :sip:ref:`~PyQt6.QtCore.QStandardPaths.standardLocations` exists or is accessible.

The following table gives examples of paths on different operating systems. The first path is the writable path (unless noted). Other, additional paths, if any, represent non-writable locations.

+-----------------------+--------------------------------------------------------------------------------------------------------------+---------------------------------------------------------------------------------------------------------------------------------+
| Path type             | macOS                                                                                                        | Windows                                                                                                                         |
+=======================+==============================================================================================================+=================================================================================================================================+
| DesktopLocation       | "~/Desktop"                                                                                                  | "C:/Users/<USER>/Desktop"                                                                                                       |
+-----------------------+--------------------------------------------------------------------------------------------------------------+---------------------------------------------------------------------------------------------------------------------------------+
| DocumentsLocation     | "~/Documents"                                                                                                | "C:/Users/<USER>/Documents"                                                                                                     |
+-----------------------+--------------------------------------------------------------------------------------------------------------+---------------------------------------------------------------------------------------------------------------------------------+
| FontsLocation         | "~/Library/Fonts", "/Library/Fonts", "/System/Library/Fonts"                                                 | "C:/Windows/Fonts" (not writable)                                                                                               |
+-----------------------+--------------------------------------------------------------------------------------------------------------+---------------------------------------------------------------------------------------------------------------------------------+
| ApplicationsLocation  | "~/Applications", "/Applications"                                                                            | "C:/Users/<USER>/AppData/Roaming/Microsoft/Windows/Start Menu/Programs"                                                         |
+-----------------------+--------------------------------------------------------------------------------------------------------------+---------------------------------------------------------------------------------------------------------------------------------+
| MusicLocation         | "~/Music"                                                                                                    | "C:/Users/<USER>/Music"                                                                                                         |
+-----------------------+--------------------------------------------------------------------------------------------------------------+---------------------------------------------------------------------------------------------------------------------------------+
| MoviesLocation        | "~/Movies"                                                                                                   | "C:/Users/<USER>/Videos"                                                                                                        |
+-----------------------+--------------------------------------------------------------------------------------------------------------+---------------------------------------------------------------------------------------------------------------------------------+
| PicturesLocation      | "~/Pictures"                                                                                                 | "C:/Users/<USER>/Pictures"                                                                                                      |
+-----------------------+--------------------------------------------------------------------------------------------------------------+---------------------------------------------------------------------------------------------------------------------------------+
| TempLocation          | randomly generated by the OS                                                                                 | "C:/Users/<USER>/AppData/Local/Temp"                                                                                            |
+-----------------------+--------------------------------------------------------------------------------------------------------------+---------------------------------------------------------------------------------------------------------------------------------+
| HomeLocation          | "~"                                                                                                          | "C:/Users/<USER>"                                                                                                               |
+-----------------------+--------------------------------------------------------------------------------------------------------------+---------------------------------------------------------------------------------------------------------------------------------+
| AppLocalDataLocation  | "~/Library/Application Support/<APPNAME>", "/Library/Application Support/<APPNAME>". "<APPDIR>/../Resources" | "C:/Users/<USER>/AppData/Local/<APPNAME>", "C:/ProgramData/<APPNAME>", "<APPDIR>", "<APPDIR>/data", "<APPDIR>/data/<APPNAME>"   |
+-----------------------+--------------------------------------------------------------------------------------------------------------+---------------------------------------------------------------------------------------------------------------------------------+
| CacheLocation         | "~/Library/Caches/<APPNAME>", "/Library/Caches/<APPNAME>"                                                    | "C:/Users/<USER>/AppData/Local/<APPNAME>/cache"                                                                                 |
+-----------------------+--------------------------------------------------------------------------------------------------------------+---------------------------------------------------------------------------------------------------------------------------------+
| StateLocation         | "~/Library/Preferences/<APPNAME>/State"                                                                      | "C:/Users/<USER>/AppData/Local/<APPNAME>/State", "C:/ProgramData/<APPNAME>/State"                                               |
+-----------------------+--------------------------------------------------------------------------------------------------------------+---------------------------------------------------------------------------------------------------------------------------------+
| GenericDataLocation   | "~/Library/Application Support", "/Library/Application Support"                                              | "C:/Users/<USER>/AppData/Local", "C:/ProgramData", "<APPDIR>", "<APPDIR>/data"                                                  |
+-----------------------+--------------------------------------------------------------------------------------------------------------+---------------------------------------------------------------------------------------------------------------------------------+
| RuntimeLocation       | "~/Library/Application Support"                                                                              | "C:/Users/<USER>"                                                                                                               |
+-----------------------+--------------------------------------------------------------------------------------------------------------+---------------------------------------------------------------------------------------------------------------------------------+
| ConfigLocation        | "~/Library/Preferences", "/Library/Preferences"                                                              | "C:/Users/<USER>/AppData/Local/<APPNAME>", "C:/ProgramData/<APPNAME>"                                                           |
+-----------------------+--------------------------------------------------------------------------------------------------------------+---------------------------------------------------------------------------------------------------------------------------------+
| GenericConfigLocation | "~/Library/Preferences", "/Library/Preferences"                                                              | "C:/Users/<USER>/AppData/Local", "C:/ProgramData"                                                                               |
+-----------------------+--------------------------------------------------------------------------------------------------------------+---------------------------------------------------------------------------------------------------------------------------------+
| DownloadLocation      | "~/Downloads"                                                                                                | "C:/Users/<USER>/Downloads"                                                                                                     |
+-----------------------+--------------------------------------------------------------------------------------------------------------+---------------------------------------------------------------------------------------------------------------------------------+
| GenericCacheLocation  | "~/Library/Caches", "/Library/Caches", "/System/Library/Caches"                                              | "C:/Users/<USER>/AppData/Local/cache"                                                                                           |
+-----------------------+--------------------------------------------------------------------------------------------------------------+---------------------------------------------------------------------------------------------------------------------------------+
| GenericStateLocation  | "~/Library/Preferences/State"                                                                                | "C:/Users/<USER>/AppData/Local/State", "C:/ProgramData/State"                                                                   |
+-----------------------+--------------------------------------------------------------------------------------------------------------+---------------------------------------------------------------------------------------------------------------------------------+
| AppDataLocation       | "~/Library/Application Support/<APPNAME>", "/Library/Application Support/<APPNAME>". "<APPDIR>/../Resources" | "C:/Users/<USER>/AppData/Roaming/<APPNAME>", "C:/ProgramData/<APPNAME>", "<APPDIR>", "<APPDIR>/data", "<APPDIR>/data/<APPNAME>" |
+-----------------------+--------------------------------------------------------------------------------------------------------------+---------------------------------------------------------------------------------------------------------------------------------+
| AppConfigLocation     | "~/Library/Preferences/<APPNAME>", "/Library/Preferences/<APPNAME>"                                          | "C:/Users/<USER>/AppData/Local/<APPNAME>", "C:/ProgramData/<APPNAME>"                                                           |
+-----------------------+--------------------------------------------------------------------------------------------------------------+---------------------------------------------------------------------------------------------------------------------------------+
| PublicShareLocation   | "~/Public"                                                                                                   | "C:/Users/Public"                                                                                                               |
+-----------------------+--------------------------------------------------------------------------------------------------------------+---------------------------------------------------------------------------------------------------------------------------------+
| TemplatesLocation     | not supported                                                                                                | "C:/Users/<USER>/AppData/Roaming/Microsoft/Windows/Templates"                                                                   |
+-----------------------+--------------------------------------------------------------------------------------------------------------+---------------------------------------------------------------------------------------------------------------------------------+

**Note:** On macOS, when the application is sandboxed, the operating system transparently redirects the user's home directory to a per-application container at ``~/Library/Containers/<BUNDLE-ID>/Data``. The macOS table above still applies, with ``~`` effectively resolving to ``<APPROOT>`` for user-rooted entries. System-wide fallbacks such as ``/Library/...``, ``/System/Library/...``, and ``<APPDIR>/../Resources`` are listed for symmetry but are typically not reachable without explicit entitlements.

+-----------------------+-------------------------------------------------------------------------------------------+
| Path type             | Linux and other UNIX operating systems                                                    |
+=======================+===========================================================================================+
| DesktopLocation       | "~/Desktop"                                                                               |
+-----------------------+-------------------------------------------------------------------------------------------+
| DocumentsLocation     | "~/Documents"                                                                             |
+-----------------------+-------------------------------------------------------------------------------------------+
| FontsLocation         | "~/.fonts", "~/.local/share/fonts", "/usr/local/share/fonts", "/usr/share/fonts"          |
+-----------------------+-------------------------------------------------------------------------------------------+
| ApplicationsLocation  | "~/.local/share/applications", "/usr/local/share/applications", "/usr/share/applications" |
+-----------------------+-------------------------------------------------------------------------------------------+
| MusicLocation         | "~/Music"                                                                                 |
+-----------------------+-------------------------------------------------------------------------------------------+
| MoviesLocation        | "~/Videos"                                                                                |
+-----------------------+-------------------------------------------------------------------------------------------+
| PicturesLocation      | "~/Pictures"                                                                              |
+-----------------------+-------------------------------------------------------------------------------------------+
| TempLocation          | "/tmp"                                                                                    |
+-----------------------+-------------------------------------------------------------------------------------------+
| HomeLocation          | "~"                                                                                       |
+-----------------------+-------------------------------------------------------------------------------------------+
| AppLocalDataLocation  | "~/.local/share/<APPNAME>", "/usr/local/share/<APPNAME>", "/usr/share/<APPNAME>"          |
+-----------------------+-------------------------------------------------------------------------------------------+
| CacheLocation         | "~/.cache/<APPNAME>"                                                                      |
+-----------------------+-------------------------------------------------------------------------------------------+
| StateLocation         | "~/.local/state/<APPNAME>"                                                                |
+-----------------------+-------------------------------------------------------------------------------------------+
| GenericDataLocation   | "~/.local/share", "/usr/local/share", "/usr/share"                                        |
+-----------------------+-------------------------------------------------------------------------------------------+
| RuntimeLocation       | "/run/user/<USER>"                                                                        |
+-----------------------+-------------------------------------------------------------------------------------------+
| ConfigLocation        | "~/.config", "/etc/xdg"                                                                   |
+-----------------------+-------------------------------------------------------------------------------------------+
| GenericConfigLocation | "~/.config", "/etc/xdg"                                                                   |
+-----------------------+-------------------------------------------------------------------------------------------+
| DownloadLocation      | "~/Downloads"                                                                             |
+-----------------------+-------------------------------------------------------------------------------------------+
| GenericCacheLocation  | "~/.cache"                                                                                |
+-----------------------+-------------------------------------------------------------------------------------------+
| GenericStateLocation  | "~/.local/state"                                                                          |
+-----------------------+-------------------------------------------------------------------------------------------+
| AppDataLocation       | "~/.local/share/<APPNAME>", "/usr/local/share/<APPNAME>", "/usr/share/<APPNAME>"          |
+-----------------------+-------------------------------------------------------------------------------------------+
| AppConfigLocation     | "~/.config/<APPNAME>", "/etc/xdg/<APPNAME>"                                               |
+-----------------------+-------------------------------------------------------------------------------------------+
| PublicShareLocation   | "~/Public"                                                                                |
+-----------------------+-------------------------------------------------------------------------------------------+
| TemplatesLocation     | "~/Templates"                                                                             |
+-----------------------+-------------------------------------------------------------------------------------------+

+----------------------------------------------+----------------------------------------------------------+-----------------------------------------------------+
| Path type                                    | Android                                                  | iOS                                                 |
+==============================================+==========================================================+=====================================================+
| DesktopLocation                              | "<APPROOT>/files"                                        | "<APPROOT>/Documents/Desktop"                       |
+----------------------------------------------+----------------------------------------------------------+-----------------------------------------------------+
| DocumentsLocation                            | "<USER>/Documents" [\*], "<USER>/<APPNAME>/Documents"    | "<APPROOT>/Documents"                               |
+----------------------------------------------+----------------------------------------------------------+-----------------------------------------------------+
| FontsLocation                                | "/system/fonts" (not writable)                           | "<APPROOT>/Library/Fonts"                           |
+----------------------------------------------+----------------------------------------------------------+-----------------------------------------------------+
| ApplicationsLocation                         | not supported (directory not readable)                   | not supported                                       |
+----------------------------------------------+----------------------------------------------------------+-----------------------------------------------------+
| MusicLocation                                | "<USER>/Music" [\*], "<USER>/<APPNAME>/Music"            | "<APPROOT>/Documents/Music"                         |
+----------------------------------------------+----------------------------------------------------------+-----------------------------------------------------+
| MoviesLocation                               | "<USER>/Movies" [\*], "<USER>/<APPNAME>/Movies"          | "<APPROOT>/Documents/Movies"                        |
+----------------------------------------------+----------------------------------------------------------+-----------------------------------------------------+
| PicturesLocation                             | "<USER>/Pictures" [\*], "<USER>/<APPNAME>/Pictures"      | "<APPROOT>/Documents/Pictures", "assets-library://" |
+----------------------------------------------+----------------------------------------------------------+-----------------------------------------------------+
| TempLocation                                 | "<APPROOT>/cache"                                        | "<APPROOT>/tmp"                                     |
+----------------------------------------------+----------------------------------------------------------+-----------------------------------------------------+
| HomeLocation                                 | "<APPROOT>/files"                                        | system defined                                      |
+----------------------------------------------+----------------------------------------------------------+-----------------------------------------------------+
| AppLocalDataLocation                         | "<APPROOT>/files", "<USER>/<APPNAME>/files"              | "<APPROOT>/Library/Application Support"             |
+----------------------------------------------+----------------------------------------------------------+-----------------------------------------------------+
| CacheLocation                                | "<APPROOT>/cache", "<USER>/<APPNAME>/cache"              | "<APPROOT>/Library/Caches"                          |
+----------------------------------------------+----------------------------------------------------------+-----------------------------------------------------+
| StateLocation                                | "<APPROOT>/files/state"                                  | "<APPROOT>/Library/Preferences/<APPNAME>/State"     |
+----------------------------------------------+----------------------------------------------------------+-----------------------------------------------------+
| GenericStateLocation (there is shared state) | "<APPROOT>/files/state"                                  | "<APPROOT>/Library/Preferences/State"               |
+----------------------------------------------+----------------------------------------------------------+-----------------------------------------------------+
| GenericDataLocation                          | "<USER>" [\*] or "<USER>/<APPNAME>/files"                | "<APPROOT>/Library/Application Support"             |
+----------------------------------------------+----------------------------------------------------------+-----------------------------------------------------+
| RuntimeLocation                              | "<APPROOT>/cache"                                        | "<APPROOT>/Library/Application Support"             |
+----------------------------------------------+----------------------------------------------------------+-----------------------------------------------------+
| ConfigLocation                               | "<APPROOT>/files/settings"                               | "<APPROOT>/Library/Preferences"                     |
+----------------------------------------------+----------------------------------------------------------+-----------------------------------------------------+
| GenericConfigLocation                        | "<APPROOT>/files/settings" (there is no shared settings) | "<APPROOT>/Library/Preferences"                     |
+----------------------------------------------+----------------------------------------------------------+-----------------------------------------------------+
| DownloadLocation                             | "<USER>/Downloads" [\*], "<USER>/<APPNAME>/Downloads"    | "<APPROOT>/Documents/Downloads"                     |
+----------------------------------------------+----------------------------------------------------------+-----------------------------------------------------+
| GenericCacheLocation                         | "<APPROOT>/cache" (there is no shared cache)             | "<APPROOT>/Library/Caches"                          |
+----------------------------------------------+----------------------------------------------------------+-----------------------------------------------------+
| AppDataLocation                              | "<APPROOT>/files", "<USER>/<APPNAME>/files"              | "<APPROOT>/Library/Application Support"             |
+----------------------------------------------+----------------------------------------------------------+-----------------------------------------------------+
| AppConfigLocation                            | "<APPROOT>/files/settings"                               | "<APPROOT>/Library/Preferences/<APPNAME>"           |
+----------------------------------------------+----------------------------------------------------------+-----------------------------------------------------+
| PublicShareLocation                          | not supported                                            | "<APPROOT>/Public"                                  |
+----------------------------------------------+----------------------------------------------------------+-----------------------------------------------------+
| TemplatesLocation                            | not supported                                            | not supported                                       |
+----------------------------------------------+----------------------------------------------------------+-----------------------------------------------------+

In the table above, ``<APPNAME>`` is usually the organization name, the application name, or both, or a unique name generated at packaging. Similarly, <APPROOT> is the location where this application is installed (often a sandbox). <APPDIR> is the directory containing the application executable.

The paths above should not be relied upon, as they may change according to OS configuration, locale, or they may change in future Qt versions.

**Note:** On Android, applications with open files on the external storage (<USER> locations), will be killed if the external storage is unmounted.

**Note:** On Android 6.0 (API 23) or higher, the "WRITE_EXTERNAL_STORAGE" permission must be requested at runtime when using :sip:ref:`~PyQt6.QtCore.QStandardPaths.writableLocation` or :sip:ref:`~PyQt6.QtCore.QStandardPaths.standardLocations`.

**Note:** On Android, reading/writing to GenericDataLocation needs the READ_EXTERNAL_STORAGE/WRITE_EXTERNAL_STORAGE permission granted.

**Note:** [\*] On Android 11 and above, public directories are no longer directly accessible in scoped storage mode. Thus, paths of the form ``"<USER>/DirName"`` are not returned. Instead, you can use :sip:ref:`~PyQt6.QtWidgets.QFileDialog` which uses the Storage Access Framework (SAF) to access such directories.

**Note:** On iOS, if you do pass ``QStandardPaths::standardLocations(QStandardPaths::PicturesLocation).last()`` as argument to :sip:ref:`~PyQt6.QtWidgets.QFileDialog.setDirectory`, a native image picker dialog will be used for accessing the user's photo album. The filename returned can be loaded using :sip:ref:`~PyQt6.QtCore.QFile` and related APIs. This feature was added in Qt 5.5.

.. seealso:: :sip:ref:`~PyQt6.QtCore.QStandardPaths.writableLocation`, :sip:ref:`~PyQt6.QtCore.QStandardPaths.standardLocations`, :sip:ref:`~PyQt6.QtCore.QStandardPaths.displayName`, :sip:ref:`~PyQt6.QtCore.QStandardPaths.locate`, :sip:ref:`~PyQt6.QtCore.QStandardPaths.locateAll`.
