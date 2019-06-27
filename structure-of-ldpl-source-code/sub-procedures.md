# SUB-PROCEDUREs

A SUB-PROCEDURE is a piece of code that can be called and executed from other parts of the script. SUB-PROCEDURE subsections must be declared within the [PROCEDURE](procedure-section.md) section of the code using a `SUB-PROCEDURE <name>` statement and end with an `END SUB-PROCEDURE` statement. Bear in mind that you can't define a SUB-PROCEDURE within a SUB-PROCEDURE. Also bear in mind that you can [CALL](../control-flow-statements/call-sub-procedure.md) a SUB-PROCEDURE before it has been declared, but the compilation process will fail if the compiler doesn't find the SUB-PROCEDURE once it has parsed all the files in your program.

The full syntax for declaring sub-procedures is this one:

```coffeescript
SUB-PROCEDURE procedureName
    PARAMETERS:
        < parameters go here >
    LOCAL DATA:
        < local variable declarations go here >
    PROCEDURE:
        < code goes here >
END SUB-PROCEDURE
```

The `PARAMETERS:` and `LOCAL DATA:` sub-sections are optional \(more on these later\). If you decide to not include both the `PARAMETERS:` and `LOCAL DATA:` sub-sections, you can skip the `PROCEDURE:` tag and just go ahead writing your code like this:

```coffeescript
SUB mySub
    # Your code goes here! For example
    DISPLAY "I love sub-procedures!" crlf
END SUB
```

As shown in the example above, the statements `SUB` and `END SUB` can be used instead of `SUB-PROCEDURE` and `END SUB-PROCEDURE`, if you prefer.

In context, the full declaration of a SUB-PROCEDURE looks like this:

```coffeescript
DATA:
  # ...
PROCEDURE:
  # ...
  SUB-PROCEDURE mySubprocedure
    PARAMETERS:
        # Parameters declaration
    LOCAL DATA:
        # Local variables declaration
    PROCEDURE:
        # Sub procedure code
        # goes here.
  END SUB-PROCEDURE
```

Of course, you cannot have two SUB-PROCEDUREs with the same name. SUB-PROCEDURE names follow the same naming guidelines variable names [follow](../naming-rules.md).

SUB-PROCEDUREs have three sub-sections: `PARAMETERS:`, `LOCAL DATA:` and `PROCEDURE:`. Again, the first two sub-sections are optional and only `PROCEDURE:` is mandatory, but you can skip the `PROCEDURE:` label if you only use this section, like this:

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

In the `PROCEDURE:` sub-section, you write the code of the SUB-PROCEDURE using statements like in the main `PROCEDURE:` section, with the addition of the [RETURN](../control-flow-statements/return.md) statement.

In `PARAMETERS:` and `LOCAL DATA:` you can only use variable declaration statements, just like in the [DATA section](data-section/). The variables defined here can only be used inside the `PROCEDURE:` sub-section of the SUB-PROCEDURE where they are declared; you can declare variables with names declared in other SUB-PROCEDURE or in the main `DATA:` section, but bear in mind that if you use these variables in your SUB-PROCEDURE code, they will always refer to the ones you declared within the SUB-PROCEDURE. For example:

```coffeescript
DATA:
  i IS number
PROCEDURE:
  SUB-PROCEDURE mySubprocedure
    LOCAL DATA:
        i IS text
    PROCEDURE:
        STORE "I'm a variable from mySubprocedure! " IN i
        DISPLAY i
  END SUB-PROCEDURE

  STORE 42 IN i
  CALL mySubprocedure
  DISPLAY i
  # The output of this program is "I'm a variable from mySubprocedure! 42"
```

At the start of the SUB-PROCEDURE execution, all the variables declared in `LOCAL DATA:` will be initialized with its [default value](../variables-in-ldpl/default-variable-values.md), and each invocation of the SUB-PROCEDURE will have its own copy of the local variables. This is important if you want to implement a recursive SUB-PROCEDURE, for example:

```coffeescript
DATA:
  executions IS number
PROCEDURE:
  SUB-PROCEDURE myRecursiveSubprocedure
    LOCAL DATA:
        myLocalVar IS number
    PROCEDURE:
        INCR executions
        IF executions IS EQUAL TO 3 THEN
            RETURN  # We don't want this to run forever!
        END IF
        DISPLAY "[myLocalVar starts at " myLocalVar "!"
        STORE executions IN myLocalVar
        CALL myRecursiveSubprocedure
        DISPLAY "I'm execution Nº " myLocalVar "!]"
  END SUB-PROCEDURE

  CALL myRecursiveSubprocedure
  # The output of this program is
  # "[myLocalVar starts at 0![myLocalVar starts at 0!I'm execution Nº 2!]I'm execution Nº 1!]"
```

Variables declared in `PARAMETERS:` are quite different, they will start with the value passed from the [CALL](../control-flow-statements/call-sub-procedure.md) using the `WITH` keyword. **Variables are passed by reference**. This means that if you modify a parameter in a SUB-PROCEDURE, the variable passed in the `CALL` will also be modified. Be careful with this, and make sure to copy a parameter in a local variable if you need it. Passing variables by reference lets you return results from your SUB-PROCEDURE, for example:

```coffeescript
DATA:
  i IS number
PROCEDURE:
  SUB-PROCEDURE duplicate
    PARAMETERS:
        input IS number
        result IS number
    PROCEDURE:
        IN result solve input + input
  END SUB-PROCEDURE

  CALL duplicate WITH 2 i
  DISPLAY i
  # The output of this program is "4"
```

