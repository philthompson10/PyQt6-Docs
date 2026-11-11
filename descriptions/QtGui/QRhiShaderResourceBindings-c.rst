.. sip:class-description::
    :status: todo
    :brief: Encapsulates resources for making buffer, texture, sampler resources visible to shaders
    :digest: 4507c52a9a2dca13d426e6853f5aa41b

Encapsulates resources for making buffer, texture, sampler resources visible to shaders.

A :sip:ref:`~PyQt6.QtGui.QRhiShaderResourceBindings` is a collection of :sip:ref:`~PyQt6.QtGui.QRhiShaderResourceBinding` objects, each of which describe a single binding.

Take a fragment shader with the following interface:

::

    layout(std140, binding = 0) uniform buf {
        mat4 mvp;
        int flip;
    } ubuf;

    layout(binding = 1) uniform sampler2D tex;

To make resources visible to the shader, the following :sip:ref:`~PyQt6.QtGui.QRhiShaderResourceBindings` could be created and then passed to QRhiGraphicsPipeline::setShaderResourceBindings():

::

    QRhiShaderResourceBindings *srb = rhi->newShaderResourceBindings();
    srb->setBindings({
        QRhiShaderResourceBinding::uniformBuffer(0, QRhiShaderResourceBinding::VertexStage | QRhiShaderResourceBinding::FragmentStage, ubuf),
        QRhiShaderResourceBinding::sampledTexture(1, QRhiShaderResourceBinding::FragmentStage, texture, sampler)
    });
    srb->create();
    // ...
    QRhiGraphicsPipeline *ps = rhi->newGraphicsPipeline();
    // ...
    ps->setShaderResourceBindings(srb);
    ps->create();
    // ...
    cb->setGraphicsPipeline(ps);
    cb->setShaderResources(); // binds srb

This assumes that ``ubuf`` is a :sip:ref:`~PyQt6.QtGui.QRhiBuffer`, ``texture`` is a :sip:ref:`~PyQt6.QtGui.QRhiTexture`, while *sampler* is a :sip:ref:`~PyQt6.QtGui.QRhiSampler`. The example also assumes that the uniform block is present in the vertex shader as well so the same buffer is made visible to the vertex stage too.

.. _qrhishaderresourcebindings-advanced-usage:

Advanced usage
^^^^^^^^^^^^^^

Building on the above example, let's assume that a pass now needs to use the exact same pipeline and shaders with a different texture. Creating a whole separate :sip:ref:`~PyQt6.QtGui.QRhiGraphicsPipeline` just for this would be an overkill. This is why :sip:ref:`~PyQt6.QtGui.QRhiCommandBuffer.setShaderResources` allows specifying a *srb* argument. As long as the layouts (so the number of bindings and the binding points) match between two :sip:ref:`~PyQt6.QtGui.QRhiShaderResourceBindings`, they can both be used with the same pipeline, assuming the pipeline was created with one of them in the first place. See :sip:ref:`~PyQt6.QtGui.QRhiShaderResourceBindings.isLayoutCompatible` for more details.

::

    QRhiShaderResourceBindings *srb2 = rhi->newShaderResourceBindings();
    // ...
    cb->setGraphicsPipeline(ps);
    cb->setShaderResources(srb2); // binds srb2

**Note:** This is a RHI API with limited compatibility guarantees, see :sip:ref:`~PyQt6.QtGui.QRhi` for details.
