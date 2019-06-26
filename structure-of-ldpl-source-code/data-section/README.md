# DATA Section

As stated in [Structure of LDPL Source Code](../), LDPL programs are divided in two sections, one of them being the **DATA** section. The DATA section is where global variables are declared (you can use them anywhere in your program). If no variables are declared, the DATA section can be skipped altogether.

All variables in LDPL have a defined [data type](data-types.md).

{% hint style="info" %}
 Available data types are `NUMBER`, `TEXT`, `NUMBER LIST`, `TEXT LIST`, `NUMBER MAP` and `TEXT MAP`.
{% endhint %}

The DATA section is defined and preceded by the `DATA:` keyword. An empty data section looks like this:

```coffeescript
DATA:

```

On every line within the DATA section \(that is, on every line after the `DATA:` keyword and before the [`PROCEDURE:`](../procedure-section.md) keyword\) one and only one variable can be declared.

The syntax for declaring a variable in LDPL is:

```coffeescript
variable name IS data type
```

{% hint style="info" %}
**Variable names** should follow the rules stated [here](../../naming-rules.md).
{% endhint %}

A DATA section cannot contain anything but variable declarations, comments and empty lines. En example DATA section may end up looking like this:

```coffeescript
DATA: #This is the DATA section
  myNumber IS NUMBER
  #Next I'm going to declare a text vector
  niceTextMap IS TEXT NUMBER
  myAwesomeList IS NUMBER LIST # I've declared a number list!

PROCEDURE:
  #This is a comment within the PROCEDURE section!
```
