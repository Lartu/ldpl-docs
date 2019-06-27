---
description: Introduced in LDPL 3.1.0 - Diligent Dreadnoughtus
---

# PUSH - TO

The `PUSH - TO` statement is used to add elements to a LIST. When you push an element to a LIST it is appended at the end of the list.

## Syntax:

```coffeescript
PUSH <NUMBER-VAR or NUMBER> TO <NUMBER-LIST>
PUSH <TEXT-VAR or TEXT> TO <TEXT-LIST>
```

## Example:

```coffeescript
DATA:
  foo IS TEXT LIST
PROCEDURE:
  PUSH "First index" TO foo
  PUSH "Second index" TO foo
```

In the above example, `foo` now contains the value `"First index"` at index `0` and the value `"Second index"` at index `1`.

