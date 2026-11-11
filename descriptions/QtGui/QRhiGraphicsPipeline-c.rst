.. sip:class-description::
    :status: todo
    :brief: Graphics pipeline state resource
    :digest: 95d80e3ef5858db6447b6ecb4a25e5c2

Graphics pipeline state resource.

Represents a graphics pipeline. What exactly this map to in the underlying native graphics API, varies. Where there is a concept of pipeline objects, for example with Vulkan, the :sip:ref:`~PyQt6.QtGui.QRhi` backend will create such an object upon calling create(). Elsewhere, for example with OpenGL, the :sip:ref:`~PyQt6.QtGui.QRhiGraphicsPipeline` may merely collect the various state, and create()'s main task is to set up the corresponding shader program, but deferring looking at any of the requested state to a later point.

As with all :sip:ref:`~PyQt6.QtGui.QRhiResource` subclasses, the two-phased initialization pattern applies: setting any values via the setters, for example setDepthTest(), is only effective after calling create(). Avoid changing any values once the :sip:ref:`~PyQt6.QtGui.QRhiGraphicsPipeline` has been initialized via create(). To change some state, set the new value and call create() again. However, that will effectively release all underlying native resources and create new ones. As a result, it may be a heavy, expensive operation. Rather, prefer creating multiple pipelines with the different states, and :sip:ref:`~PyQt6.QtGui.QRhiCommandBuffer.setGraphicsPipeline` when recording the render pass.

**Note:** Setting the shader stages is mandatory. There must be at least one stage, and there must be a vertex stage.

**Note:** Setting the shader resource bindings is mandatory. The referenced :sip:ref:`~PyQt6.QtGui.QRhiShaderResourceBindings` must already have create() called on it by the time create() is called. Associating with a :sip:ref:`~PyQt6.QtGui.QRhiShaderResourceBindings` that has no bindings is also valid, as long as no shader in any stage expects any resources. Using a :sip:ref:`~PyQt6.QtGui.QRhiShaderResourceBindings` object that does not specify any actual resources (i.e., the buffers, textures, etc. for the binding points are set to ``nullptr``) is valid as well, as long as a :sip:ref:`~PyQt6.QtGui.QRhiShaderResourceBindings.isLayoutCompatible` :sip:ref:`~PyQt6.QtGui.QRhiShaderResourceBindings`, that specifies resources for all the bindings, is going to be set via :sip:ref:`~PyQt6.QtGui.QRhiCommandBuffer.setShaderResources` when recording the render pass.

**Note:** Setting the render pass descriptor is mandatory. To obtain a :sip:ref:`~PyQt6.QtGui.QRhiRenderPassDescriptor` that can be passed to setRenderPassDescriptor(), use either QRhiTextureRenderTarget::newCompatibleRenderPassDescriptor() or QRhiSwapChain::newCompatibleRenderPassDescriptor().

**Note:** Setting the vertex input layout is mandatory.

**Note:** sampleCount() defaults to 1 and must match the sample count of the render target's color and depth stencil attachments.

**Note:** The depth test, depth write, and stencil test are disabled by default. The face culling mode defaults to no culling.

**Note:** stencilReadMask() and stencilWriteMask() apply to both faces. They both default to 0xFF.

.. _qrhigraphicspipeline-example-usage:

Example usage
.............

All settings of a graphics pipeline have defaults which might be suitable to many applications. Therefore a minimal example of creating a graphics pipeline could be the following. This assumes that the vertex shader takes a single ``vec3 position`` input at the input location 0. With the :sip:ref:`~PyQt6.QtGui.QRhiShaderResourceBindings` and :sip:ref:`~PyQt6.QtGui.QRhiRenderPassDescriptor` objects, plus the :sip:ref:`~PyQt6.QtGui.QShader` collections for the vertex and fragment stages, a pipeline could be created like this:

::

    QRhiShaderResourceBindings *srb;
    QRhiRenderPassDescriptor *rpDesc;
    QShader vs, fs;
    // ...

    QRhiVertexInputLayout inputLayout;
    inputLayout.setBindings({ { 3 * sizeof(float) } });
    inputLayout.setAttributes({ { 0, 0, QRhiVertexInputAttribute::Float3, 0 } });

    QRhiGraphicsPipeline *ps = rhi->newGraphicsPipeline();
    ps->setShaderStages({ { QRhiShaderStage::Vertex, vs }, { QRhiShaderStage::Fragment, fs } });
    ps->setVertexInputLayout(inputLayout);
    ps->setShaderResourceBindings(srb);
    ps->setRenderPassDescriptor(rpDesc);
    if (!ps->create()) { error(); }

The above code creates a pipeline object that uses the defaults for many settings and states. For example, it will use a :sip:ref:`~PyQt6.QtGui.QRhiGraphicsPipeline.Topology.Triangles` topology, no backface culling, blending is disabled but color write is enabled for all four channels, depth test/write are disabled, stencil operations are disabled.

**Note:** This is a RHI API with limited compatibility guarantees, see :sip:ref:`~PyQt6.QtGui.QRhi` for details.

.. seealso:: :sip:ref:`~PyQt6.QtGui.QRhiCommandBuffer`, :sip:ref:`~PyQt6.QtGui.QRhi`.
