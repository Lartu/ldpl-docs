# LOAD FILE - IN

The `LOAD FILE` statement loads the contents of a file into a text variable.

#### Syntax:

```coffeescript
LOAD FILE <TEXT or TEXT-VAR> IN <TEXT-VAR>
```

#### Example:

```coffeescript
LOAD FILE "myFolder/myTextFile.txt" IN myVariable
```

#### Error codes:

If the LOAD operation should fail, the following values will be returned into the `ERRORCODE` and `ERRORTEXT` variables:

* `ERRORCODE`: 1
* `ERRORTEXT`: "The file '&lt;filename&gt;' couldn't be opened."

{% hint style="warning" %}
Always use the `ERRORCODE` variable to check if the operation was successful or not. Do **not** use `ERRORTEXT` for anything else than displaying the error found, as its contents may change in future releases of LDPL.
{% endhint %}

