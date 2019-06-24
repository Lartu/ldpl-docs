---
description: Introduced in LDPL 3.0.5 - Creative Carnotaurus
---

# GET INDEX OF - FROM - IN

The `GET INDEX OF - FROM - IN` statement stores in a NUMBER variable the position of the first occurrence of a specified value in a string or TEXT variable. The first position of a string \(the first letter\) is considered to be the position number `0`. The value `-1` is stored if there are no occurrences.

#### Syntax:

```coffeescript
GET INDEX OF <TEXT or TEXT-VAR> FROM <TEXT or TEXT-VAR> IN <NUMBER-VAR>
```

#### Example:

```coffeescript
DATA:
  position IS NUMBER
PROCEDURE:
  GET INDEX OF "is" FROM "LDPL is nice!" IN position
  DISPLAY position CRLF
  # Will display 5.
```



