# EXECUTE

The `EXECUTE` statement executes the specified system command.

#### Syntax:

```coffeescript
EXECUTE <TEXT or TEXT-VAR>
```

#### Example 1:

```coffeescript
# Prepare the command to execute
IN myTextVar JOIN "echo " myVariable " >> myFile"
# Execute it
EXECUTE myTextVar
```

#### Example 2:

```coffeescript
# Execute "dir" to list the files in the current directory under Windows
EXECUTE "dir"
```

