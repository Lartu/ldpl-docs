---
description: Introduced in LDPL 3.0.6 - Diligent Dreadnoughtus
---

# Declaring LIST Variables

A **LIST** is a sequence of values, called **elements**. The elements of a LIST are distinguished by their indices. **Indices** are NUMBER literals that start at 0 \(the first element of the list\) and grow up to the length of the list minus one \(the last element of the list\). LISTs in LDPL are variables that hold a collection of values. When you declare a LIST, you declare a structure that lets you store values of its type one after another. For example, say you declare the list`myList`:

```coffeescript
DATA:
  myList IS NUMBER LIST
```

Then you can use `myList` as a multi-variable with various indexes where you can store NUMBERs.

LDPL provides one-dimensional LISTs for storing groups of related strings or numbers \(but not at the same time: LISTs can be either `NUMBER LIST` or `TEXT LIST` and each can only be used to store values of the chosen data type\).

In most other languages, you may have to **declare** a LIST and specify how many elements or components it contains. In such languages, the declaration causes a contiguous block of memory to be allocated for that many elements. LDPL LISTs, however, are different: they are **dynamic**. This means that you can store as many values as you want in a single LIST without fear of running out of place \(of course, this is limited by the memory allocated by your operating system for your LDPL program\).

Suppose you store the values `"hi"`, `"there"`, `"I love"` and `"LDPL, it's great!"` in a `TEXT LIST`, in that particular order. Then the contents of the list and the **index** associated with each **element** will be

| Index | Element |
| :---: | :---: |
| 0 | `"hi"` |
| 1 | `"there"` |
| 2 | `"I love"` |
| 3 | `"LDPL, it's great!"` |

We have shown the pairs in order because their order is relevant: if you added a new element to the LIST, it would be inserted after the last element, thus being associated with index `5`.

To add values to a LIST, you must first push them to the list. For example, if you want to add the numbers `10`, `20` and `30` to a `NUMBER LIST`, your code should look like this:

```coffeescript
DATA:
  myList IS NUMBER LIST
PROCEDURE:
  PUSH 10 TO myList # 10 is stored in index 0 of myList
  PUSH 20 TO myList # 20 is stored in index 1 of myList
  PUSH 30 TO myList # 30 is stored in index 2 of myList
```

Values in LISTs can be stored and accessed just like any other variable \(see the [STORE - IN](../control-flow-statements/store-in.md) statement for further details\) using the `:` operator. This operator indicates what index of the LIST we are writing to or reading from. Here we declare a `NUMBER LIST` and store the values `5` and `-10.2` in it, and then replace the number `5` by the number `890`:

```coffeescript
DATA:
  myList IS NUMBER LIST
PROCEDURE:
  PUSH 5 TO myList # 5 is stored in index 0 of myList
  PUSH -10.2 TO myList # -10.2 is stored in index 1 of myList
  STORE 890 IN myList:0 #We store 890 in index 0 of myList, thus replacing the 5
```

Please note that as a LIST is **variable** that's a collection of values, a single index of a LIST is a variable in itself. This means that any subindex of a LIST can be used in any position where you could use a variable of the same type of the LIST. So, if you have something like this:

```coffeescript
STORE <NUMBER-VAR or NUMBER> IN <NUMBER-VAR>
```

You could use a `NUMBER LIST` with a defined sub-index \(for example, in the example above, `myList:0`\) where it says NUMBER-VAR, just like in the `STORE - IN` examples in the code extracts above.

In the **LIST STATEMENTS** section you'll find a collection of statements that can be used to work with LISTs.

