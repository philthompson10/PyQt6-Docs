.. sip:enum-member-description::
    :status: todo
    :value: 0x2000
    :digest: 7cb3f619e2e505603cacdc82a98a396b

Indicates that values of this type are immutable; for instance, because they are pointers to const objects.

**Note:** Before Qt 6.5, both the NeedsConstruction and NeedsDestruction flags were incorrectly set if the either copy construtor or destructor were non-trivial (that is, if the type was not trivial).
