# REPLACE - FROM - WITH - IN

The `REPLACE` statement finds and replaces every occurrence of some TEXT in a TEXT variable or value some other TEXT.  The result is then stored in a TEXT variable.

**Syntax:**

```c
REPLACE <TEXT-VAR or TEXT> FROM <TEXT-VAR or TEXT> WITH <TEXT-VAR or TEXT> IN <TEXT-VAR>
```

**Example:**

```coffeescript
REPLACE "LDPL" FROM "LDPL is great!" WITH "🦕" IN sentiment
DISPLAY sentiment crlf
```

Outputs:

```text
🦕 is great!
```

