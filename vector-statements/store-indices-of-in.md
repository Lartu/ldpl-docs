---
description: Introduced in LDPL 3.0.5 - Creative Carnotaurus
---

# GET KEYS OF - IN

The `GET KEYS OF - IN` statement stores all the keys of a MAP into a TEXT LIST. Say you have a MAP with keys `0`, `"cat"` and `"dog"`. The elements these keys point to are not important. Using the `GET KEYS OF` statement, you can copy the keys of this MAP to a LIST. Thus, the resulting LIST will \(for example\) have the value `0` at index 0, the value `"cat"` at index 1 and the value `"dog"` at index 2. This statement is thus used to find all the keys of a particular MAP.

## Syntax:

```coffeescript
GET KEYS OF <MAP> IN <TEXT-LIST>
```

## Example:

```coffeescript
DATA:
  foo IS TEXT MAP
  bar IS TEXT LIST
PROCEDURE:
  STORE "Hello there!" IN foo:0
  STORE "How are you?" IN foo:7
  STORE "I like cats" IN foo:"cat"
  STORE "I love dogs" IN foo:"dog"
  STORE "LDPL is nice" IN foo:3
  GET KEYS OF foo IN bar
```

At the end of the execution of the previous excerpt of code, the `TEXT LIST` called `bar` will contain the values `"0"`, `"7"`, `"cat"`, `"dog"` and `"3"` at indexes that are consecutive integers starting at zero.

