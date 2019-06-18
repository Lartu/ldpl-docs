---
description: Introduced in LDPL 3.0.5 - Creative Carnotaurus
---

# COPY - TO

The `COPY - TO` statement copies all the elements of a MAP with their respective keys to another MAP **of the same type**. The original MAP is untouched, but the destination MAP is completely overwritten by the contents of the copied MAP and any elements that existed in it prior to the copy are deleted. In other words, the destination MAP is [CLEAR](clear.md)ed before the copy.

#### Syntax:

```coffeescript
COPY <TEXT-MAP> TO <TEXT-MAP>
COPY <NUMBER-MAP> TO <NUMBER-MAP>
```

#### Example:

```coffeescript
DATA:
  foo IS TEXT MAP
  bar IS TEXT MAP
PROCEDURE:
  STORE "Hello there!" IN foo:0
  STORE "How are you?" IN foo:7
  COPY foo TO bar
  DISPLAY bar:0 " " bar:7 CRLF
  # Will display "Hello there! How are you?"
```

