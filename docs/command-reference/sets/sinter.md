---
description: Intersect multiple sets
---

# SINTER

## Syntax

    SINTER key [key ...]

**Time complexity:** O(N*M) worst case where N is the cardinality of the smallest set and M is the number of sets.

Returns the members of the set resulting from the intersection of all the given
sets.

For example:

```
key1 = {a,b,c,d}
key2 = {c}
key3 = {a,c,e}
SINTER key1 key2 key3 = {c}
```

Keys that do not exist are considered to be empty sets.
With one of the keys being an empty set, the resulting set is also empty (since
set intersection with an empty set always results in an empty set).

## Return

[Array reply](https://redis.io/docs/reference/protocol-spec#resp-arrays): list with members of the resulting set.

## Examples

```cli
SADD key1 "a"
SADD key1 "b"
SADD key1 "c"
SADD key2 "c"
SADD key2 "d"
SADD key2 "e"
SINTER key1 key2
```