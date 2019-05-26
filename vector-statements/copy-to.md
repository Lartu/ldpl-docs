---
description: Introduced in LDPL 3.0.5 - Creative Carnotaurus
---

# COPY - TO

The `COPY - TO` statement copies all the elements of a vector with their respective indices to another vector **of the same type**. The original vector is untouched, but the destination vector is completely overwritten by the contents of the copied vector and any elements that existed in it prior to the copy are deleted. In other words, the destination vector is [CLEAR](clear.md)ED before the copy.

#### Syntax:

```coffeescript
COPY <TEXT-VECTOR> TO <TEXT-VECTOR>
COPY <NUMBER-VECTOR> TO <NUMBER-VECTOR>
```

#### Example:

```coffeescript
DATA:
  foo IS TEXT VECTOR
  bar IS TEXT VECTOR
PROCEDURE:
  STORE "Hello there!" IN foo:0
  STORE "How are you?" IN foo:7
  COPY foo TO bar
  DISPLAY bar:0 " " bar:7 CRLF
  # Will display "Hello there! How are you?"
```

