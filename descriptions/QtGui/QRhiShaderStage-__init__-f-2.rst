.. sip:method-description::
    :status: todo
    :pysig: 1d7d69a8d05b40e7b081268eb1620f8b
    :realsig: (QRhiShaderStage::Type, const QShader&, QShader::Variant)
    :digest: a26172d5027f711fed7c0d2626770c7b

Constructs a shader stage description with the *type* of the stage and the *shader*.

The shader variant *v* defaults to :sip:ref:`~PyQt6.QtGui.QShader.Variant.StandardShader`. A :sip:ref:`~PyQt6.QtGui.QShader` contains multiple source and binary versions of a shader. In addition, it can also contain variants of the shader with slightly modified code. *v* can then be used to select the desired variant.
