---
description: Introduced in LDPL 3.1.0 - Diligent Dreadnoughtus
---

# STORE LENGTH OF - IN

The `STORE LENGTH OF - IN` statement stores the amount of elements stored in a LIST \(or, analogously, the length of the LIST\) into a numeric variable.

## Syntax:

```coffeescript
STORE LENGHT OF <LIST> IN <NUMBER-VAR>
```

## Example:

```coffeescript
DATA:
  foo IS TEXT LIST
  count IS NUMBER
PROCEDURE:
  PUSH "Hello there!" TO foo
  PUSH "How are you?" TO foo
  STORE LENGTH OF foo IN count
  DISPLAY count CRLF
  # Will display 2
```

