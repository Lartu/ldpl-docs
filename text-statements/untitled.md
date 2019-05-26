---
description: Introduced in LDPL 3.0.5 - Creative Carnotaurus
---

# SUBSTRING - FROM - LENGTH - IN

The `SUBSTRING - FROM - LENGTH - IN` statement extracts parts of a string, beginning at the character at the specified position and storing in the destination TEXT variable the specified number of characters.

#### Syntax:

```coffeescript
SUBSTRING <TEXT or TEXT-VAR> FROM <NUMBER or NUMBER-VAR> LENGTH <NUMBER or NUMBER-VAR> IN <TEXT-VAR>
```

#### Example:

```coffeescript
DATA:
  foo IS TEXT
PROCEDURE:
  SUBSTRING "Hello there!" FROM 1 LENGTH 4 IN foo
  # This will extract 4 characters from position 1
  DISPLAY foo CRLF
  # Will display "ello"
```



