# CALL SUB-PROCEDURE

The `CALL SUB-PROCEDURE` statement executes a SUB-PROCEDURE. Once the SUB-PROCEDURE returns, the execution continues from the line following the `CALL SUB-PROCEDURE`.

## Syntax:

```coffeescript
CALL SUB-PROCEDURE <sub-procedure name>
CALL SUB-PROCEDURE <sub-procedure name> WITH <multiple NUMBER, TEXT, TEXT-VAR, NUMBER-VAR, MAP or LIST>
```

or just

```coffeescript
CALL <sub-procedure name>
CALL <sub-procedure name> WITH <multiple NUMBER, TEXT, TEXT-VAR, NUMBER-VAR, MAP or LIST>
```

Of course, a [SUB-PROCEDURE must be declared](../structure-of-ldpl-source-code/sub-procedures.md) somewhere in your program if you call it.

If the SUB-PROCEDURE you call doesn't have declared parameters, you must call it without the `WITH` keyword, otherwise you must include it and after it pass all the parameters in the same order declared in the `PARAMETERS` section of the SUB-PROCEDURE. Remember that variables are passed by reference, see the [SUB-PROCEDUREs documentation](../structure-of-ldpl-source-code/sub-procedures.md) for more details.

