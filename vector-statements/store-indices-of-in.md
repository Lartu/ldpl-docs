---
description: Introduced in LDPL 3.0.5 - Creative Carnotaurus
---

# STORE INDICES OF - IN

The `STORE INDICES OF - IN` statement stores all the indices of a vector into another vector. Say you have a vector with indices `0`, `"cat"` and `"dog"`. The elements these indices point to are not important. Using the `STORE INDICES OF` statement, you can copy the indices of this vector to another vector as elements. Thus, the resulting vector will \(for example\) have the value `0` at index 0, the value `"cat"` at index 1 and the value `"dog"` at index 2 \(the order is not relevant and no ordering criteria is provided\). This statement is thus used to find all the indices of a particular vector.

#### Syntax:

```coffeescript
STORE INDICES OF <VECTOR> IN <TEXT-VECTOR>
```

#### Example:

```coffeescript
DATA:
  foo IS TEXT VECTOR
  bar IS TEXT VECTOR
PROCEDURE:
  STORE "Hello there!" IN foo:0
  STORE "How are you?" IN foo:7
  STORE "I like cats" IN foo:"cat"
  STORE "I love dogs" IN foo:"dog"
  STORE "LDPL is nice" IN foo:3
  STORE INDICES OF foo IN bar
```

At the end of the execution of the previous excerpt of code, the TEXT vector `bar` will contain the values `"0"`, `"7"`, `"cat"`, `"dog"` and `"3"` in indices that are consecutive integers starting at zero, but in no particular order \(meaning that `"0"` may come before `"7"` or after it, no ordering criteria is provided by this standard\).

