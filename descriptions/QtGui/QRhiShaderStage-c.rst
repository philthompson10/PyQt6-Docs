.. sip:class-description::
    :status: todo
    :brief: Specifies the type and the shader code for a shader stage in the pipeline
    :digest: 68c88f6f4c70331baec1d39c3d0a0672

Specifies the type and the shader code for a shader stage in the pipeline.

When setting up a :sip:ref:`~PyQt6.QtGui.QRhiGraphicsPipeline`, a collection of shader stages are specified. The :sip:ref:`~PyQt6.QtGui.QRhiShaderStage` contains a :sip:ref:`~PyQt6.QtGui.QShader` and some associated metadata, such as the graphics pipeline stage, and the :sip:ref:`~PyQt6.QtGui.QShader.Variant` to select. There is no need to specify the shader language or version because the :sip:ref:`~PyQt6.QtGui.QRhi` backend in use at runtime will take care of choosing the appropriate shader version from the collection within the :sip:ref:`~PyQt6.QtGui.QShader`.

The typical usage is in combination with QRhiGraphicsPipeline::setShaderStages(), shown here with a simple approach to load the :sip:ref:`~PyQt6.QtGui.QShader` from ``.qsb`` files generated offline or at build time:

::

    QShader getShader(const QString &name)
    {
        QFile f(name);
        return f.open(QIODevice::ReadOnly) ? QShader::fromSerialized(f.readAll()) : QShader();
    }

    QShader vs = getShader("material.vert.qsb");
    QShader fs = getShader("material.frag.qsb");
    pipeline->setShaderStages({
        { QRhiShaderStage::Vertex, vs },
        { QRhiShaderStage::Fragment, fs }
    });

**Note:** This is a RHI API with limited compatibility guarantees, see :sip:ref:`~PyQt6.QtGui.QRhi` for details.
