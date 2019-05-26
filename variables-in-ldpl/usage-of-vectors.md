# Usage of VECTORs

A **vector** is a table of values, called **elements**. The elements of a vector are distinguished by their indices. **Indices** may be either NUMBER or TEXT literals. Vectors in LDPL are variables that hold a collection of values. When you declare a vector, you declare a structure that lets you store values of its type on any sub-index of the variable. For example, say you declare the vector `myVector`:

```coffeescript
DATA:
  myVector IS NUMBER VECTOR
```

Then you can use `myVector` as a multivariable with various indexes where you can store NUMBERs.

LDPL provides one-dimensional vectors for storing groups of related strings or numbers.

In most other languages, you have to **declare** an array \(other languages' equivalents of LDPL vectors\) and specify how many elements or components it contains. In such languages, the declaration causes a contiguous block of memory to be allocated for that many elements. An index in the array usually must be a positive integer; for example, the index zero specifies the first element in the array, which is actually stored at the beginning of the block of memory. Index one specifies the second element, which is stored in memory right after the first element, and so on. It is impossible to add more elements to the array, because it has room for only as many elements as you declared \(some languages allow arbitrary starting and ending indices, e.g., `15 .. 27`, but the size of the array is still fixed when the array is declared\).

LDPL vectors different: they are **associative**. This means that each vector is a collection of pairs: an index, and its corresponding vector element value:

| Index | Value |
| :---: | :---: |
| 4 | 30 |
| 2 | 10 |
| "Hi there!" | -56.3 |
| "99ldplrocks89" | 0 |

We have shown the pairs in jumbled order because their order is irrelevant. One advantage of associative vectors is that new pairs can be added at any time. Vectors can be sparse: it can have missing indices \(say for example you have indices 1 and 5, but don't have indices 2, 3 and 4\). Another consequence of associative vectors is that the indices don't have to be positive integers. Any number, or even a string, can be an index.

Values in vectors can be stored and accessed just like any other variable \(see the [STORE - IN](../control-flow-statements/store-in.md) statement for further details\). Here we declare a NUMBER vector and store the values `5` and `-10.2` in the indices `1` and `5`, respectively.

```coffeescript
DATA:
  myVector IS NUMBER VECTOR
PROCEDURE:
  STORE 5 IN myVector:1 #Stores 5 in the subindex 1 of myVector
  STORE -10.2 IN myVector:5 #Stores -10.2 in the subindex 5 of myVector
```

As stated before, vector sub-indexes don't always have to be constant NUMBERs. They can also be NUMBER variables, TEXT and TEXT variables, or even sub-indexes of other arrays. For example:

```coffeescript
DATA:
  myVector IS NUMBER VECTOR
  myOtherVector IS NUMBER VECTOR
  myVar IS NUMBER

PROCEDURE:
  STORE 17 IN myVar
  STORE 1 IN myVector:"hello" #Stores 1 in the subindex "hello" of myVector
  STORE 7 IN myVector:myVar #Stores 7 in the position of index value of myVar
  STORE 3 IN myVector:myOtherVector:4
  #Stores 3 in the position of index value of myVar of myOtherVector
```

In fact, when you use a NUMBER value as a subindex for a VECTOR, it is silently casted into a TEXT value. For example, `myVector:1` will be interpreted \(an thus, the same\) as `myVector:"1"`.

Please note that as a VECTOR is **variable** that's a collection of values, a single index of a VECTOR is a variable in itself. This means that any subindex of a VECTOR can be used in any position where you could use a variable of the same type of the vector. So, if you have something like this:

```coffeescript
STORE <NUMBER-VAR or NUMBER> IN <NUMBER-VAR>
```

You could use a NUMBER VECTOR with a defined sub-index where it says NUMBER-VAR, just like in the `STORE - IN` examples in the code extracts above.

When LDPL creates an array for you, e.g., with the [SPLIT ](../text-statements/split-by-in.md)built-in statement, that vector's indices are consecutive integers starting at zero \(`0`, `1`, `2`, etc.\).

As you'll see in the [Default Variable Values](default-variable-values.md) section, you can access undeclared indices of a vector just like if they were declared. See the following example:

```coffeescript
DATA:
  myVector IS NUMBER VECTOR
PROCEDURE:
  DISPLAY myVector:99
```

In the example above, `0` will be printed and no errors displayed during compilation, even though the index `99` of `myVector` hasn't been explicitly declared. This is because when you try to access an element that hasn't been declared yet, LDPL declares it for you and initializes it to its type default value.

It's important to note that this very feature is a double-edged weapon. While you can use it to access uninitialized vector positions, you cannot check if a value exists in a vector without initializing it if it wasn't there before. Statements like [STORE INDEX COUNT OF](../vector-statements/store-index-count-of-in.md) and [STORE INDICES OF](../vector-statements/store-indices-of-in.md) are provided as means to overcome this situation.

\(Also, as some parts of LDPL vectors work just like arrays do in awk, some parragraphs of this section are heavily based on the ones found on [http://kirste.userpage.fu-berlin.de/chemnet/use/info/gawk/gawk\_12.html](http://kirste.userpage.fu-berlin.de/chemnet/use/info/gawk/gawk_12.html)\).

