.. sip:method-description::
    :status: todo
    :pysig: 7e42f4080e1ed0b2e41b452b4fdbaba3
    :realsig: (QRhiResourceUpdateBatch*)
    :digest: 466999ab1690b6884402b1b30da814d4

Copies all queued operations from the *other* batch into this one.

**Note:** *other* may no longer contain valid data after the merge operation, and must not be submitted, but it will still need to be released by calling :sip:ref:`~PyQt6.QtGui.QRhiResourceUpdateBatch.release`.

This allows for a convenient pattern where resource updates that are already known during the initialization step are collected into a batch that is then merged into another when starting to first render pass later on:

::

    void init()
    {
        initialUpdates = rhi->nextResourceUpdateBatch();
        initialUpdates->uploadStaticBuffer(vbuf, vertexData);
        initialUpdates->uploadStaticBuffer(ibuf, indexData);
        // ...
    }

    void render()
    {
        QRhiResourceUpdateBatch *resUpdates = rhi->nextResourceUpdateBatch();
        if (initialUpdates) {
            resUpdates->merge(initialUpdates);
            initialUpdates->release();
            initialUpdates = nullptr;
        }
        // resUpdates->updateDynamicBuffer(...);
        cb->beginPass(rt, clearCol, clearDs, resUpdates);
    }
