.. sip:enum-member-description::
    :status: todo
    :value: 0x04000000
    :digest: 024afce64ad652eab30cdb9ebaa84288

Informs the window system that the window should stay on bottom of all other windows.

**Note:** On X11, this hint will work only in window managers that support _NET_WM_STATE_BELOW atom. If a window always on the bottom has a parent, the parent will also be left on the bottom. This window hint is currently not implemented for macOS.

**Note:** On Windows, this will work only for frameless or full-screen windows.
