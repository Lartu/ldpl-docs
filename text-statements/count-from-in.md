---
description: Introduced in LDPL 3.0.5 - Creative Carnotaurus
---

# COUNT - FROM - IN

The `COUNT - FROM - IN` statement counts all the appearances of a string in another string and stores that value in a NUMBER variable.

#### Syntax:

```coffeescript
COUNT <TEXT or TEXT-VAR> FROM <TEXT or TEXT-VAR> IN <NUMBER-VAR>
```

#### Example:

```coffeescript
DATA:
  count IS NUMBER
PROCEDURE:
  COUNT "the" FROM "the cat is called theodore" IN count
  DISPLAY count CRLF
  # Will display 2, as the can be found two times in that sentence.
```



