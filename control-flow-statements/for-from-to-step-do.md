---
description: Introduced in LDPL 3.0.6 - Diligent Dreadnoughtus
---

# FOR - FROM - TO - STEP - DO

The `FOR` statement repeatedly run the code in its body a number of times, given a `counter` variable, the `start` of the range, its `end` and a `step`.

When the loop starts, `start` is assigned to `counter` and starts an iteration, evaluating a condition. The condition is `counter <= end` if `step >= 0` and `counter >= end` if `step < 0`. If the condition passes, the code in the body of the `FOR` is executed, otherwise the loop will end. After the code is ran the `counter` is incremeted by `step` and a new iteration is started (checking the condition and so on).

#### Syntax:

```coffeescript
FOR <NUMBER-VAR> FROM <NUMBER-VAR or NUMBER> TO <NUMBER-VAR or NUMBER> STEP <NUMBER-VAR or NUMBER> DO
 #Code goes here
NEXT
```

#### Example:

```coffeescript
DATA:
  i IS NUMBER
PROCEDURE:
  FOR i FROM 0 TO 10 STEP 2 DO
    DISPLAY i " "
  NEXT
  # Will display "0 2 4 6 8 10"
```
