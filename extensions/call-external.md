# CALL EXTERNAL

The `CALL EXTERNAL` statement executes a SUB-PROCEDURE defined in an extension to LDPL, typically in C++. It otherwise operates the same as `CALL SUB-PROCEDURE`, except that external SUB-PROCEDURES do not receive parameters.

#### Syntax:

```text
CALL EXTERNAL <external sub-procedure name>
```

**Example:**

```text
CALL EXTERNAL http-get
```



