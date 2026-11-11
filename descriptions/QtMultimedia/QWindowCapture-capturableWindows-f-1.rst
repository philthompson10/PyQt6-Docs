.. sip:method-description::
    :status: todo
    :pysig: ffe8a571d44306a91bc3e7bf597ce0de
    :realsig: ()
    :digest: aa334a7e668d3f3d5d792ebe81c61426

Returns a list of :sip:ref:`~PyQt6.QtMultimedia.QCapturableWindow` objects that are currently available for capturing.

**Note:** On macOS, invoking this method will trigger the "Screen Recording" permission dialog. If permissions have not yet been granted, this method will return an empty list. Invoking it multiple times will bring this dialog to the foreground.
