---
description: Introduced in LDPL 3.0.5 - Creative Carnotaurus
---

# TRIM - IN

The `TRIM - IN` statement removes whitespace from both sides of a string and stores the resulting string in a TEXT variable.

#### Syntax:

```coffeescript
TRIM <TEXT or TEXT-VAR> IN <TEXT-VAR>
```

#### Example:

```coffeescript
DATA:
  foo IS TEXT
PROCEDURE:
  TRIM "        hello there!            " IN foo
  DISPLAY foo CRLF
  # Will display "hello there!"
```



