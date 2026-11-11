.. sip:enum-description::
    :status: todo
    :digest: cb287a7e36dcc96ef234419eb2751b19

Describes the desired output format when serializing the :sip:ref:`~PyQt6.QtGui.QShader`.

The default value for the ``version`` argument of :sip:ref:`~PyQt6.QtGui.QShader.serialized` is ``Latest``. This is sufficient in the vast majority of cases. Specifying another value is needed only when the intention is to generate serialized data that can be loaded by earlier Qt versions. For example, the ``qsb`` tool uses these enum values when the ``--qsbversion`` command-line argument is given.

**Note:** Targeting earlier versions will make certain features disfunctional with the generated asset. This is not an issue when using the asset with the specified, older Qt version, given that that Qt version does not have the newer features in newer Qt versions that rely on additional data generated in the :sip:ref:`~PyQt6.QtGui.QShader` and the serialized data stream, but may become a problem if the generated asset is then used with a newer Qt version.
