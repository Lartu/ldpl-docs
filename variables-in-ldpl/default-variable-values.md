# Default Variable Values

In LDPL each variable is initialized with a value by default. This means that when you declare a variable, it will, by default, hold this value until it's changed.

**NUMBER** variables are initialized with the value `0`. Each element of a **NUMBER MAP** is a NUMBER variable, and thus also initialized to `0`.

**TEXT** variables are initialized to the empty string `""`. Same goes to **TEXT MAP**s, where each element is also initialized to `""`.

**LIST**s are initialized empty by default and trying to access a non-existing index will result in an error.

