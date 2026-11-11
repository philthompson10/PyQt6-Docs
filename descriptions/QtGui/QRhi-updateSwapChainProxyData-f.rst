.. sip:method-description::
    :status: todo
    :pysig: 4942116d99c6ce28f81380c79fe11d15
    :realsig: (QRhi::Implementation, QWindow*)
    :digest: 27d366cdf386cf4189280e9306e67740

Generates and returns a :sip:ref:`~PyQt6.QtGui.QRhiSwapChainProxyData` struct containing opaque data specific to the backend and graphics API specified by *impl*. *window* is the :sip:ref:`~PyQt6.QtGui.QWindow` a swapchain is targeting.

The returned struct can be passed to QRhiSwapChain::setProxyData(). This makes sense in threaded rendering systems: this static function is expected to be called on the **main (gui) thread**, unlike all :sip:ref:`~PyQt6.QtGui.QRhi` operations, then transferred to the thread working with the :sip:ref:`~PyQt6.QtGui.QRhi` and :sip:ref:`~PyQt6.QtGui.QRhiSwapChain` and passed on to the swapchain. This allows doing native platform queries that are only safe to be called on the main thread, for example to query the CAMetalLayer from a NSView, and then passing on the data to the :sip:ref:`~PyQt6.QtGui.QRhiSwapChain` living on the rendering thread. With the Metal example, doing the view.layer access on a dedicated rendering thread causes a warning in the Xcode Thread Checker. With the data proxy mechanism, this is avoided.

When threads are not involved, generating and passing on the :sip:ref:`~PyQt6.QtGui.QRhiSwapChainProxyData` is not required: backends are guaranteed to be able to query whatever is needed on their own, and if everything lives on the main (gui) thread, that should be sufficient.

**Note:** *impl* should match what the :sip:ref:`~PyQt6.QtGui.QRhi` is created with. For example, calling with :sip:ref:`~PyQt6.QtGui.QRhi.Implementation.Metal` on a non-Apple platform will not generate any useful data.
