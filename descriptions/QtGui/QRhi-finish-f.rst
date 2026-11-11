.. sip:method-description::
    :status: todo
    :pysig: 6043b6d8623d050965b30a7744116b1d
    :realsig: ()
    :digest: b35a45c31b7e06ac60543726abf2412b

Waits for any work on the graphics queue (where applicable) to complete, then executes all deferred operations, like completing readbacks and resource releases. Can be called inside and outside of a frame, but not inside a pass. Inside a frame it implies submitting any work on the command buffer.

**Note:** Avoid this function. One case where it may be needed is when the results of an enqueued readback in a swapchain-based frame are needed at a fixed given point and so waiting for the results is desired.
