---
description: Introduced in LDPL 3.0.5 - Creative Carnotaurus
---

# STORE KEYS OF - IN

The `STORE KEYS OF - IN` statement stores all the keys of a MAP into another MAP. Say you have a MAP with keys `0`, `"cat"` and `"dog"`. The elements these keys point to are not important. Using the `STORE KEYS OF` statement, you can copy the keys of this MAP to another MAP as elements. Thus, the resulting MAP will \(for example\) have the value `0` at key 0, the value `"cat"` at key 1 and the value `"dog"` at key 2 \(the order is not relevant and no ordering criteria is provided\). This statement is thus used to find all the keys of a particular MAP.

## Syntax:

```coffeescript
STORE KEYS OF <MAP> IN <TEXT-MAP>
```

## Example:

```coffeescript
DATA:
  foo IS TEXT MAP
  bar IS TEXT MAP
PROCEDURE:
  STORE "Hello there!" IN foo:0
  STORE "How are you?" IN foo:7
  STORE "I like cats" IN foo:"cat"
  STORE "I love dogs" IN foo:"dog"
  STORE "LDPL is nice" IN foo:3
  STORE KEYS OF foo IN bar
```

At the end of the execution of the previous excerpt of code, the `TEXT MAP` called `bar` will contain the values `"0"`, `"7"`, `"cat"`, `"dog"` and `"3"` at keys that are consecutive integers starting at zero, but in no particular order \(meaning that `"0"` may come before `"7"` or after it, no ordering criteria is provided by this standard\).

{% hint style="warning" %}
Please note that as MAPs where called VECTORs prior to LDPL 3.0.6 Diligent Dreadnoughtus, this statement was called `STORE INDICES OF - IN`. While we still support and will continue to support legacy code that uses the old syntax, it is **deprecated** and should not be used anymore.
{% endhint %}

