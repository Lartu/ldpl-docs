# DISPLAY

The `DISPLAY` statement outputs the values passed to the output stream. `CRLF` means line break and is a sugar syntax for the `"\n"` [escape sequence](../variables-in-ldpl/escape-sequences.md).

#### Syntax:

```coffeescript
DISPLAY <multiple NUMBER, TEXT, TEXT-VAR, NUMBER-VAR or CRLF>
```

#### Example:

```coffeescript
DISPLAY "Hello, " nameVariable "! This is a number -> " 89.1 " :)" CRLF
```

