---
description: Introduced in LDPL 3.0.5 - Creative Carnotaurus
---

# STORE INDEX COUNT OF - IN

The `STORE INDEX COUNT OF - IN` statement stores the amount of elements \(or, analogously, indices\) stored in a vector into a numeric variable.

#### Syntax:

```coffeescript
STORE INDEX COUNT OF <VECTOR> IN <NUMBER-VAR>
```

#### Example:

```coffeescript
DATA:
  foo IS TEXT VECTOR
  count IS NUMBER
PROCEDURE:
  STORE "Hello there!" IN foo:0
  STORE "How are you?" IN foo:7
  STORE INDEX COUNT OF foo IN count
  DISPLAY count CRLF
  # Will display 2
```



