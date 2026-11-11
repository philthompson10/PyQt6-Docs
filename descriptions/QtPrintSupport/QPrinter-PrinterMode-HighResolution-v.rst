.. sip:enum-member-description::
    :status: todo
    :value: 2
    :digest: 811a77baa8f04ebb5486a7125c30a06f

On Windows, sets the printer resolution to that defined for the printer in use. For PDF printing, sets the resolution of the PDF driver to 1200 dpi.

**Note:** When rendering text on a :sip:ref:`~PyQt6.QtPrintSupport.QPrinter` device, it is important to realize that the size of text, when specified in points, is independent of the resolution specified for the device itself. Therefore, it may be useful to specify the font size in pixels when combining text with graphics to ensure that their relative sizes are what you expect.
