.. sip:class-description::
    :status: todo
    :brief: Font metrics information
    :digest: d1d25d26f58f500dbd221427cf104031

The :sip:ref:`~PyQt6.QtGui.QFontMetricsF` class provides font metrics information.

:sip:ref:`~PyQt6.QtGui.QFontMetricsF` functions calculate the size of characters and strings for a given font. You can construct a :sip:ref:`~PyQt6.QtGui.QFontMetricsF` object with an existing :sip:ref:`~PyQt6.QtGui.QFont` to obtain metrics for that font. If the font is changed later, the font metrics object is *not* updated.

Once created, the object provides functions to access the individual metrics of the font, its characters, and for strings rendered in the font.

There are several functions that operate on the font: :sip:ref:`~PyQt6.QtGui.QFontMetricsF.ascent`, :sip:ref:`~PyQt6.QtGui.QFontMetricsF.descent`, :sip:ref:`~PyQt6.QtGui.QFontMetricsF.height`, :sip:ref:`~PyQt6.QtGui.QFontMetricsF.leading` and :sip:ref:`~PyQt6.QtGui.QFontMetricsF.lineSpacing` return the basic size properties of the font. The :sip:ref:`~PyQt6.QtGui.QFontMetricsF.underlinePos`, :sip:ref:`~PyQt6.QtGui.QFontMetricsF.overlinePos`, :sip:ref:`~PyQt6.QtGui.QFontMetricsF.strikeOutPos` and :sip:ref:`~PyQt6.QtGui.QFontMetricsF.lineWidth` functions, return the properties of the line that underlines, overlines or strikes out the characters. These functions are all fast.

There are also some functions that operate on the set of glyphs in the font: :sip:ref:`~PyQt6.QtGui.QFontMetricsF.minLeftBearing`, :sip:ref:`~PyQt6.QtGui.QFontMetricsF.minRightBearing` and :sip:ref:`~PyQt6.QtGui.QFontMetricsF.maxWidth`. These are by necessity slow, and we recommend avoiding them if possible.

For each character, you can get its :sip:ref:`~PyQt6.QtGui.QFontMetricsF.horizontalAdvance`, :sip:ref:`~PyQt6.QtGui.QFontMetricsF.leftBearing`, and :sip:ref:`~PyQt6.QtGui.QFontMetricsF.rightBearing`, and find out whether it is in the font using :sip:ref:`~PyQt6.QtGui.QFontMetricsF.inFont`. You can also treat the character as a string, and use the string functions on it.

The string functions include :sip:ref:`~PyQt6.QtGui.QFontMetricsF.horizontalAdvance`, to return the width of a string in pixels (or points, for a printer), :sip:ref:`~PyQt6.QtGui.QFontMetricsF.boundingRect`, to return a rectangle large enough to contain the rendered string, and :sip:ref:`~PyQt6.QtGui.QFontMetricsF.size`, to return the size of that rectangle.

:sip:ref:`~PyQt6.QtGui.QFontMetrics` has two different functions for calculating the bounds of a string, each with multiple overloads: :sip:ref:`~PyQt6.QtGui.QFontMetricsF.boundingRect` and :sip:ref:`~PyQt6.QtGui.QFontMetricsF.tightBoundingRect`. If a precise bounding rect is needed, then :sip:ref:`~PyQt6.QtGui.QFontMetricsF.tightBoundingRect` should be preferred. This will measure each glyph individually to return a bounding rect that fits tightly around the rendered text. Depending on the platform, the :sip:ref:`~PyQt6.QtGui.QFontMetricsF.boundingRect` function may return approximated bounds, but require less computation.

Example:

.. literalinclude:: ../../../snippets/qtbase-src-gui-doc-snippets-code-src_gui_text_qfontmetrics.py
    :lines: 72-75

.. seealso:: :sip:ref:`~PyQt6.QtGui.QFont`, :sip:ref:`~PyQt6.QtGui.QFontInfo`, :sip:ref:`~PyQt6.QtGui.QFontDatabase`.
