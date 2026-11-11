.. sip:enum-member-description::
    :status: todo
    :value: 0
    :digest: d3c0d346eb5902eafbd8e2be6b5fcaa5

Indicates that the data is not expected to change ever after the initial upload. Under the hood such buffer resources are typically placed in device local (GPU) memory (on systems where applicable). Uploading new data is possible, but may be expensive. The upload typically happens by copying to a separate, host visible staging buffer from which a GPU buffer-to-buffer copy is issued into the actual GPU-only buffer.
