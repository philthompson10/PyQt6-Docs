.. sip:enum-member-description::
    :status: todo
    :value: 1 << 0
    :digest: 77d0d883f88d78c348f77eacc60e42ea

Specifies that no present command is to be queued or no swapBuffers call is to be made. This way no image is presented. Generating multiple frames with all having this flag set is not recommended (except, for example, for benchmarking purposes - but keep in mind that backends may behave differently when it comes to waiting for command completion without presenting so the results are not comparable between them)
