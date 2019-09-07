# IF - IS - THEN

The `IF` statement evaluates if the condition given is positive. If it is, the code in the positive branch is executed. If it is not, the code in the negative branch is executed \(if available\). Execution then continues normally.

## Syntax:

```coffeescript
IF <CONDITION> THEN
 #Code goes here (positive branch)
ELSE
 #Code goes here (negative branch)
END IF
```

or

```coffeescript
IF <CONDITION> THEN
 #Code goes here (positive branch)
END IF
```

The `<CONDITION>` may be a relational operator between two values with the same type:

* `<NUMBER-VAR or NUMBER> IS <REL-OP-A> <NUMBER-VAR or NUMBER>`
* `<TEXT-VAR or TEXT> IS <REL-OP-B> <TEXT-VAR or TEXT>`
* `<NUMBER LIST> IS <REL-OP-B> <NUMBER LIST>`
* `<TEXT LIST> IS <REL-OP-B> <TEXT LIST>`
* `<NUMBER MAP> IS <REL-OP-B> <NUMBER MAP>`
* `<TEXT MAP> IS <REL-OP-B> <TEXT MAP>`

**Possible values of `REL-OP-A`:**

* `EQUAL TO`
* `NOT EQUAL TO`
* `GREATER THAN`
* `LESS THAN`
* `GREATER THAN OR EQUAL TO`
* `LESS THAN OR EQUAL TO`

**Possible values of `REL-OP-B`:**

* `EQUAL TO`
* `NOT EQUAL TO`

You can also write compound conditions using `AND`, `OR` and parenthesis:

* `<CONDITION> AND <CONDITION>` is positive if both conditions are positive
* `<CONDITION> OR <CONDITION>` is positive if both conditions are positive
* `( <CONDITION> )` is positive if the condition is positive, it's used to alter the default precedence

The `AND` has higher precedence than `OR`, and the conditions inside parenthesis will be evaluated first. That means that `C1 AND C2 OR C3` is the same as `( C1 AND C2 ) OR C3`, but you can make the `OR` evaluate first if you write `C1 AND ( C2 OR C3 )`.

Both `AND` and `OR` perform short-circuit evaluation: If the first operand of an AND is negative the second will not be evaluated and the `AND` condition is determined as negative. If the first operand of an OR is positive the second will not be evaluated and the `OR` condition is determined as positive.

For example:

```coffeescript
DATA:
names IS TEXT LIST
length IS NUMBER
PROCEDURE:
GET LENGTH OF names IN length
IF length IS GREATER THAN 0 AND ( names:0 IS EQUAL TO "Alice" OR names:0 IS EQUAL TO "Bob" ) THEN
 #Code
END IF
```

The `names` list is empty, so the `length is greater than 0` condition is negative, and the second one is not evaluated \(and the execution continues after the `END IF`\). Thanks to short-circuit evaluation `names:0` is not evaluated and we don\`t get an index out of range runtime error!

