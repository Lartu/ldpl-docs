---
description: Introduced in LDPL 3.0.6 - Diligent Dreadnoughtus
---

# COPY - TO

The `COPY - TO` statement copies all the elements of a LIST with their respective indices to another MAP **of the same type**. The original LIST is untouched, but the destination LIST is completely overwritten by the contents of the copied LIST and any elements that existed in it prior to the copy are deleted. In other words, the destination LIST is [CLEAR](../vector-statements/clear.md)ed before the copy.

#### Syntax:

```coffeescript
COPY <TEXT-LIST> TO <TEXT-LIST>
COPY <NUMBER-LIST> TO <NUMBER-LIST>
```

#### Example:

```coffeescript
DATA:
  foo IS TEXT LIST
  bar IS TEXT LIST
PROCEDURE:
  STORE "Hello there!" IN foo:0
  STORE "How are you?" IN foo:7
  COPY foo TO bar
  DISPLAY bar:0 " " bar:7 CRLF
  # Will display "Hello there! How are you?"
```
