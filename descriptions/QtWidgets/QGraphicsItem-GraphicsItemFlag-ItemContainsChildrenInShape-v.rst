.. sip:enum-member-description::
    :status: todo
    :value: 0x80000
    :digest: ef92695cce43b3640180c0d088f54070

This flag indicates that all of the item's direct or indirect children only draw within the item's shape. Unlike ItemClipsChildrenToShape, this restriction is not enforced. Set ItemContainsChildrenInShape when you manually assure that drawing is bound to the item's shape and want to avoid the cost associated with enforcing the clip. Setting this flag enables more efficient drawing and collision detection. The flag is disabled by default.

**Note:** If both this flag and ItemClipsChildrenToShape are set, the clip will be enforced. This is equivalent to just setting ItemClipsChildrenToShape.
