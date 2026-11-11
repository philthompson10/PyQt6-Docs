.. sip:enum-member-description::
    :status: todo
    :value: 0xffff0000
    :digest: 1d82a8aff8c7c5c5ac5029c52b16f9b5

This mask yields nonzero if any of the exclusive flags are used.

**Note:** If several exclusive flags are OR-ed together, the resulting character set will consist of the union of the specified sets. For instance specifying ``ImhNumbersOnly`` and ``ImhUppercaseOnly`` would yield a set consisting of numbers and uppercase letters.
