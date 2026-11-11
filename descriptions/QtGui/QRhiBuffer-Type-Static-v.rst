.. sip:enum-member-description::
    :status: todo
    :value: 1
    :digest: 60c4b4c5981a1f54ac2c15ad42bed12a

Indicates that the data is expected to change only infrequently. Typically placed in device local (GPU) memory, where applicable. On backends where host visible staging buffers are used for uploading, the staging buffers are kept around for this type, unlike with Immutable, so subsequent uploads do not suffer in performance. Frequent updates, especially updates in consecutive frames, should be avoided.
