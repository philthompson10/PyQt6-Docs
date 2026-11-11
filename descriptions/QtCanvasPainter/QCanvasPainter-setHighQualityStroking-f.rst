.. sip:method-description::
    :status: todo
    :pysig: c506ff134babdd6e68ab3e6350e95305
    :realsig: (bool)
    :digest: 21b33227d6a3a644ce8f588b2db79def

Sets the high quality stroking to *enabled*. Setting this to ``true`` gives a more correct rendering in some less common cases where stroking overlaps and doesn't have full opacity. Enabling it results into higher rendering cost. The default value is ``false``.

+--------------------------------------------+----------------------------------------------------------+
| |image-qcpainter-highqualitystroking-webp| | ::                                                       |
|                                            |                                                          |
|                                            |     // Increase the line width and reduce opacity to get |
|                                            |     // the stroking flaws visible.                       |
|                                            |     p->setLineWidth(20);                                 |
|                                            |     p->setGlobalAlpha(0.5);                              |
|                                            |     if (m_path.isEmpty()) {                              |
|                                            |         m_path.moveTo(30, 30);                           |
|                                            |         m_path.lineTo(40, 30);                           |
|                                            |         m_path.lineTo(80, 170);                          |
|                                            |         m_path.lineTo(80, 30);                           |
|                                            |         m_path.lineTo(70, 30);                           |
|                                            |     }                                                    |
|                                            |     p->setHighQualityStroking(true);                     |
|                                            |     p->stroke(m_path);                                   |
|                                            |     p->setHighQualityStroking(false);                    |
|                                            |     p->translate(90, 0);                                 |
|                                            |     p->stroke(m_path);                                   |
+--------------------------------------------+----------------------------------------------------------+

.. |image-qcpainter-highqualitystroking-webp| image:: ../../../images/qcpainter-highqualitystroking.webp
