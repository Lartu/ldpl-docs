---
description: Introduced in LDPL 3.1.0 - Diligent Dreadnoughtus
---

# CREATE STATEMENT - EXECUTING

The `CREATE STATEMENT` statement lets you add custom statements to LDPL that execute SUB-PROCEDUREs.

## Syntax:

```coffeescript
CREATE STATEMENT <TEXT> EXECUTING <sub-procedure name>
```

The `TEXT` describes the new statement syntax and must contain tokens separated by whitespace. Each token can be a keyword, which is a word with `A-Z` characters (preferably in English), or `"$"`, a character that marks where parameters are passed. At least one keyword token is required and the number of `"$"` tokens must be the same as the number of parameters of the SUB-PROCEDURE you pass after `EXECUTING`. For example, a valid `TEXT` is `"DISPLAY $ $ TIMES"` if the SUB-PROCEDURE has exactly two parameters. The SUB-PROCEDURE must be declared before creating the statement.

After a statement is created you can use it like any other LDPL statement in `PROCEDURE` sections, just write a line with all the tokens of the `TEXT` in the same order but placing values instead of `"$"`. The types of the values must be the same as the parameter types of the SUB-PROCEDURE the statement executes following the same order. Using the new statement will produce the same effect as [CALL](call-sub-procedure.md)ing the SUB-PRODUCE (parameters are passed by reference too).

You can create two different statements with same `TEXT` and use both if one of the parameter types are different, because the resulting syntaxes will differ from each other. Using this you can create two versions of the same statements dealing with different parameters type, like the first example shows.

Bear in mind that a line in your program could match more than one statement: If all of them were created with `CREATE STATEMENT`, the one that was created first will be executed. If one of the them is a LDPL built-in statement, this will be executed. For example, if you create `"DISPLAY $ $ TIMES"`, declare a variable `TIMES` and use the line `DISPLAY "Hi!" 3 TIMES"`, the LDPL [DISPLAY](../i-o-statements/display.mpd) statement will be executed, because the line matches its syntax. This is illustrated in the second example.

## Example 1:

```coffeescript
PROCEDURE:
  SUB-PROCEDURE displayNValueTimes
    PARAMETERS:
      value is number
      times is number
    LOCAL DATA:
      i is number
    PROCEDURE:
      FOR i FROM 0 TO times STEP 1 DO
        DISPLAY value " "
      REPEAT
  END SUB-PROCEDURE
  CREATE STATEMENT "DISPLAY $ $ TIMES" EXECUTING displayNValueTimes
  # Syntax for this new statement: DISPLAY <NUMBER or NUMBER-VAR> <NUMBER or NUMBER-VAR> TIMES

  SUB-PROCEDURE displayTValueTimes
    PARAMETERS:
      value is text
      times is number
    LOCAL DATA:
      i is number
    PROCEDURE:
      FOR i FROM 0 to times STEP 1 DO
        DISPLAY value " "
      REPEAT
  END SUB-PROCEDURE
  CREATE STATEMENT "DISPLAY $ $ TIMES" EXECUTING displayTValueTimes
  # Syntax for this new statement: DISPLAY <TEXT or TEXT-VAR> <NUMBER or NUMBER-VAR> TIMES

  # We can imagine that we have only one statement:
  # DISPLAY <NUMBER or NUMBER-VAR or TEXT or TEXT-VAR> <NUMBER or NUMBER-VAR> TIMES

  DISPLAY 100 2 TIMES # This executes: CALL displayNValueTimes with 100 2
  DISPLAY "Hi!" 3 TIMES # This executes: CALL displayTValueTimes with "Hi!" 3

  # This program displays "100 100 Hi! Hi! "
```

## Example 2:

```coffeescript
DATA:
  times is number
PROCEDURE:
  SUB-PROCEDURE displayTValueTimes
    PARAMETERS:
      value is text
      times is number
    LOCAL DATA:
      i is number
    PROCEDURE:
      FOR i FROM 0 to times STEP 1 DO
        DISPLAY value " "
      REPEAT
  END SUB-PROCEDURE
  CREATE STATEMENT "DISPLAY $ $ TIMES" EXECUTING displayTValueTimes
  # Syntax for this new statement: DISPLAY <TEXT or TEXT-VAR> <NUMBER or NUMBER-VAR> TIMES

  DISPLAY "Hi!" 3 TIMES # This executes the LDPL DISPLAY statement!

  # This program displays "Hi!30" because times is equal to 0
  ```
