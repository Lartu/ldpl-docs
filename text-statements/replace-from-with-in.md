# REPLACE - FROM - WITH - IN

The `REPLACE` statement will find and replace every occurrence of some TEXT with some other TEXT, then place the resulting value in a TEXT-VAR. 

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

