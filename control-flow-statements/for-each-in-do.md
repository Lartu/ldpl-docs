---
description: Introduced in LDPL 3.1.0 - Diligent Dreadnoughtus
---

# FOR EACH - IN - DO

The `FOR EACH` statement repeatedly run the code in its body for every element in a given `LIST` or `MAP`. At the start of each iteration an element of the collection is assigned to a variable matching its type.

If the collection is a `LIST`, its elements will be iterated increasingly from index `0`, while in the case of a `MAP` all the elements will be iterated in no particular order.

## Syntax:

```coffeescript
FOR EACH <NUMBER-VAR> IN <NUMBER-LIST or NUMBER-MAP> DO
 #Code goes here
REPEAT
FOR EACH <TEXT-VAR> IN <TEXT-LIST or TEXT-MAP> DO
 #Code goes here
REPEAT
```

## Example 1:

```coffeescript
DATA:
  letter IS TEXT
  letters IS TEXT LIST
PROCEDURE:
  PUSH "L" TO letters
  PUSH "D" TO letters
  PUSH "P" TO letters
  PUSH "L" TO letters
  FOR EACH letter IN letters DO
    DISPLAY letter
  REPEAT
  # Will display "LDPL"
```

## Example 2:

```coffeescript
DATA:
  number IS NUMBER
  numbers IS NUMBER MAP
PROCEDURE:
  STORE 1 IN numbers:"One"
  STORE 2 IN numbers:"Two"
  STORE 3 IN numbers:"Three"
  FOR EACH number IN numbers DO
    DISPLAY number
  REPEAT
  # Will display "312" or any permutation
```

