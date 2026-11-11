.. sip:method-description::
    :status: todo
    :pysig: d41d8cd98f00b204e9800998ecf8427e
    :realsig: ()
    :digest: 1031aa2a25c1a1c34f922a7bddb34e44

Call this function when the content of the offscreen color buffer should be updated. (i.e. to request that :sip:ref:`~PyQt6.QtQuick.QQuickRhiItemRenderer.render` is called again; the call will happen at a later point, and note that updates are typically throttled to the presentation rate)

This function can be called from :sip:ref:`~PyQt6.QtQuick.QQuickRhiItemRenderer.render` to schedule an update.

**Note:** This function should be used from inside the renderer. To update the item on the GUI thread, use QQuickRhiItem::update().
