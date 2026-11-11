.. sip:enum-member-description::
    :status: todo
    :value: '_'
    :digest: 1211528c61632321c51536d1269cf9d1

Use ``'_'``, the underscore character.

**Note:** Although dash and underscore are the only separators used in public standards (as at 2023), it is possible to cast any `ASCII <https://en.cppreference.com/w/cpp/language/ascii>`_ character to this type if a non-standard ASCII separator is needed. Casting a non-ASCII character (with decimal value above 127) is not supported: such values are reserved for future use as enum members if some public standard ever uses a non-ASCII separator. It is, of course, possible to use QString::replace() to replace the separator used by a function taking a parameter of this type with an arbitrary Unicode character or string.
