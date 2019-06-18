# SUB-PROCEDUREs

A SUB-PROCEDURE is a piece of code that can be called and executed from other parts of the script. SUB-PROCEDURE subsections must be declared within the [PROCEDURE](procedure-section.md) section of the code using a `SUB-PROCEDURE <name>` statement and end with an `END SUB-PROCEDURE` statement. Bear in mind that you can't define a SUB-PROCEDURE within a SUB-PROCEDURE. Also bear in mind that you can [CALL](../control-flow-statements/call-sub-procedure.md) a SUB-PROCEDURE before it has been declared, but the compilation process will fail if the compiler doesn't find the SUB-PROCEDURE once it has parsed all the files in your program.

The syntax for declaring sub-procedures is this one:

```coffeescript
DATA:
  # ...
PROCEDURE:
  # ...
  SUB-PROCEDURE mySubprocedure
    # Sub procedure code
    # goes here.
  END SUB-PROCEDURE
```

Of course, you cannot have two SUB-PROCEDUREs with the same name. SUB-PROCEDURE names follow the same naming guidelines variable names [follow](../naming-rules.md).

