---
description: Introduced in LDPL 3.1.0 - Diligent Dreadnoughtus
---

# LIST CONTENTS OF DIRECTORY - IN

The `LIST CONTENTS OF DIRECTORY - IN` statement does what it says on the tin: stores the names of all the files in a certain directory in a `TEXT LIST`. If the directory cannot be read \(or the directory doesn't exist, or the route passed does not lead to a directory but a regular file\) the `ERRORCODE` variable is altered and a message detailing the error is stored in the `ERRORTEXT` variable.

#### Syntax: <a id="syntax"></a>

```coffeescript
LIST CONTENTS OF DIRECTORY <TEXT or TEXT-VAR> IN <TEXT-LIST>
```

#### Example: <a id="example"></a>

```coffeescript
LIST CONTENTS OF DIRECTORY "/route/to/directory" IN listOfFiles
```

#### Error codes: <a id="error-codes"></a>

If the `LIST CONTENTS OF DIRECTORY - IN` operation should fail, the following values will be returned into the `ERRORCODE` and `ERRORTEXT` variables:

* `ERRORCODE`: 1
* `ERRORTEXT`: "Error opening directory '&lt;route&gt;'."

{% hint style="warning" %}
Always use the `ERRORCODE` variable to check if the operation was successful or not. Do **not** use `ERRORTEXT` for anything else than displaying the error found, as its contents may change in future releases of LDPL.
{% endhint %}

