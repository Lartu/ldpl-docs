# Declaring MAP variables

A **MAP** is a table of values, called **elements**. The elements of a MAP are distinguished by their keys. **Keys** may be either NUMBER or TEXT literals. MAPs in LDPL are variables that hold a collection of values. When you declare a MAP, you declare a structure that lets you store values of its type on any sub-index of the variable. For example, say you declare the map `myMap`:

```coffeescript
DATA:
  myMap IS NUMBER MAP
```

Then you can use `myMap` as a multi-variable with various indexes where you can store NUMBERs.

Unlike LISTs, MAPs are **associative**. This means that each MAP is a collection of pairs: a key and its corresponding element. For example, you could have a `NUMBER MAP` with the following contents:

| Key | Element |
| :---: | :---: |
| 4 | 30 |
| 2 | 10 |
| "Hi there!" | -56.3 |
| "99ldplrocks89" | 0 |

We have shown the pairs in jumbled order because their order is irrelevant. One advantage of MAPs is that new pairs can be added at any time. MAPs can be sparse: they can have missing keys \(say for example you have keys 1 and 5, but don't have keys 2, 3 and 4\). Another consequence of MAPs is that the keys don't necessarily have to be positive integers. Any number, or even a string, can be a key.

Values in MAPs can be stored and accessed just like any other variable \(see the [STORE - IN](../control-flow-statements/store-in.md) statement for further details\) using the `:` operator. This operator indicates what key of the MAP we are writing to or reading from. Here we declare a `NUMBER MAP` and store the values `5` and `-10.2` in the keys `1` and `5`, respectively.

```coffeescript
DATA:
  myMap IS NUMBER MAP
PROCEDURE:
  STORE 5 IN myMap:1 #Stores 5 in key 1 of myMap
  STORE -10.2 IN myMap:5 #Stores -10.2 in key 5 of myMap
```

As stated before, MAP keys don't always have to be constant NUMBERs. They can also be NUMBER variables, TEXT and TEXT variables, or even sub-indexes of LISTs or elements from other MAPs. For example:

```coffeescript
DATA:
  myMap IS NUMBER MAP
  myOtherMap IS NUMBER MAP
  myVar IS NUMBER

PROCEDURE:
  STORE 17 IN myVar
  STORE 1 IN myMap:"hello" #Stores 1 in key "hello" of myMap
  STORE 7 IN myMap:myVar #Stores 7 in a key equal to the current value of myVar
  STORE 3 IN myMap:myOtherMap:4
  #Stores 3 in a key of equal value to the key of myMap with value equal to
  #key 4 of myOtherMap
```

In fact, when you use a NUMBER value as a subindex for a MAP, it is silently casted into a TEXT value. For example, `myMap:1` will be interpreted \(an thus, the same\) as `myMap:"1"`.

Please note that as a MAP is **variable** that's a collection of values, a single key of a MAP is a variable in itself. This means that any key of a MAP can be used in any position where you could use a variable of the same type of the MAP. So, if you have something like this:

```coffeescript
STORE <NUMBER-VAR or NUMBER> IN <NUMBER-VAR>
```

You could use a `NUMBER MAP` with a particular key where it says NUMBER-VAR, just like in the `STORE - IN` examples in the code extracts above \(for example `myMap:"hello"`\).

When LDPL creates a MAP for you using a built-in statement that automatically inserts values into the MAP, for example the [SPLIT ](../text-statements/split-by-in.md)built-in statement with a MAP for destination, the keys used will be consecutive integers starting at zero \(`0`, `1`, `2`, etc.\).

As you'll see in the [Default Variable Values](default-variable-values.md) section, you can access undeclared keys of a MAP just like if they were declared. See the following example:

```coffeescript
DATA:
  myMap IS NUMBER MAP
PROCEDURE:
  DISPLAY myMap:99
```

In the example above, `0` will be printed and no errors displayed during compilation, even though the key`99` of `myMap` hasn't been explicitly declared. This is because when you try to access an element that hasn't been declared yet, LDPL declares it for you and initializes it to its type default value.

It's important to note that this very feature is a double-edged weapon. While you can use it to access uninitialized MAP keys, you cannot check if a value exists in a MAP without initializing it if it wasn't there before. Statements like [STORE KEY COUNT OF](../vector-statements/store-index-count-of-in.md) and [STORE KEYS OF](../vector-statements/store-indices-of-in.md) are provided as means to overcome this situation.

In the **MAP STATEMENTS** section you'll find a collection of statements that can be used to work with MAPs.

{% hint style="warning" %}
In older versions of LDPL, **MAP**s where called **VECTOR**s. Starting from LDPL 3.0.6 Diligent Dreadnoughtus, they have been renamed to reflect the real data structure they represent. While it is still possible to call them VECTORs in code, and legacy code that declares MAPs as VECTORs is and will continue be supported, this nomenclature is **deprecated** and shouldn't be used anymore.
{% endhint %}
