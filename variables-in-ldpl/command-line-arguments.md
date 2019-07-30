# Command Line Arguments

Every LDPL program comes with a variable declared by default: `argv`, a **TEXT LIST**. If you pass command line arguments to your LDPL compiled program \(running, for example, something like `myBinary argument1 argument2)`, the value stored in the `argv` list \(_argument vector_\) will store the values of each argument passed \(in this case, `"argument1"` will be stored in `argv:0` and `"argument2"` in `argv:1`\).

{% hint style="info" %}
Given that `argv` is a TEXT LIST, the values passed as arguments are always stored as TEXT.
{% endhint %}

Naturally, if no arguments are passed to the program, `argv` will be empty.

