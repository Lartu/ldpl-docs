---
description: Introduced in LDPL 3.0.5 - Creative Carnotaurus
---

# STORE KEY COUNT OF - IN

The `STORE KEY COUNT OF - IN` statement stores the amount of elements \(or, analogously, keys\) stored in a MAP into a numeric variable.

#### Syntax:

```coffeescript
STORE KEY COUNT OF <MAP> IN <NUMBER-MAP>
```

#### Example:

```coffeescript
DATA:
  foo IS TEXT MAP
  count IS NUMBER
PROCEDURE:
  STORE "Hello there!" IN foo:0
  STORE "How are you?" IN foo:7
  STORE KEY COUNT OF foo IN count
  DISPLAY count CRLF
  # Will display 2
```

{% hint style="warning" %}
Please note that as MAPs where called VECTORs prior to LDPL 3.0.6 Diligent Dreadnoughtus, this statement was called `STORE INDEX COUNT OF - IN`. While we still support and will continue to support legacy code that uses the old syntax, it is **deprecated** and should not be used anymore.
{% endhint %}

