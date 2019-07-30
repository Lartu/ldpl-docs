---
description: Introduced in LDPL 3.0.5 - Creative Carnotaurus
---

# GET KEY COUNT OF - IN

The `GET KEY COUNT OF - IN` statement stores the amount of elements \(or, analogously, keys\) stored in a MAP into a numeric variable.

## Syntax:

```coffeescript
GET KEY COUNT OF <MAP> IN <NUMBER-VAR>
```

## Example:

```coffeescript
DATA:
  foo IS TEXT MAP
  count IS NUMBER
PROCEDURE:
  STORE "Hello there!" IN foo:0
  STORE "How are you?" IN foo:7
  GET KEY COUNT OF foo IN count
  DISPLAY count CRLF
  # Will display 2
```

