---
description: Get all the members in a set
---

# SMEMBERS

## Syntax

    SMEMBERS key

**Time complexity:** O(N) where N is the set cardinality.

Returns all the members of the set value stored at `key`.

This has the same effect as running `SINTER` with one argument `key`.

## Return

[Array reply](https://redis.io/docs/reference/protocol-spec#resp-arrays): all elements of the set.

## Examples

```cli
SADD myset "Hello"
SADD myset "World"
SMEMBERS myset
```