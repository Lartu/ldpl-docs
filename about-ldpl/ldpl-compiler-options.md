# LDPL Compiler Switches

To compile an LDPL source file, the syntax is as follow:

`$ ldpl <ldpl_source_file> [[-i=]<ldpl_source_file>]* [flag]*`

The first part of the command, `ldpl` runs the LDPL compiler. Then it checks every other part of the command for either files
or compiler flags. Compiler flags are preceded by `-` or `--`, all the remaining tokens are considered to be files to be compiled. Except when importing source files \(more on this below\), the order of the parameters of the compilation line doesn't really matter.

You can pass the LDPL compiler as many **source files** as you want and all these files will be compiled into one big executable, respecing
the order in which they were passed to the compiler. For example, if you have three scripts `helloWorld.ldpl` \(that prints
"Hello World!" when executed\), `byeByeWorld.ldpl` \(that prints "Bye Bye World!"\) when executed, and `hiThere.ldpl` \(that prints
"Hi there~" when executed\), you could compile all three files into one single executable by running

`$ ldpl helloWorld.ldpl byeByeWorld.ldpl hiThere.ldpl`

and this would create an executable file called `helloWorld-bin`. By default, the name used to save the executable is the name
of the first LDPL source code passed to the compiler, minus the extension, plus `-bin` \(or `-bin.exe` on Windows\).

When you run `helloWorld-bin`, "Hello World! Bye Bye World! Hi there~" will be printed to the screen, respecting the order
in which the sources where compiled. If you were to change the order of the sources in the compilation line, the order of
execution of the binary file would change as well.

**Flags** alter the way the compiler works by default. The list of available flags can be found by running `$ ldpl -h`.

You can **import** files to your LDPL compilation by using the `-i=` flag. For example, say you have a library `mylib.ldpl` and a source file `mysource.ldpl`, you can compile both and include the library by running `ldpl -i=mylibrary.ldpl mysource.ldpl`. Multiple `-i=` can be used to import multiple files. While the `-i=` flag is not mandatory when including LDPL sources, as seen above, importing C++ Extensions **requires** this flag to be used; see the [Extensions](../extensions/c++-extensions/) section for more information.

By using the `-r` flag you can just transpile the project into C++ and print the **C++ representation** for that code.

You can set the **output file name** for the compiled binary with the `-o` flag. For example, if in the example above you wanted to name your program "myProgram" instead of "helloWorld-bin", you could compile it with `ldpl main.ldpl -o=myProgram`.

On **Linux** and **Windows** platforms, LDPL builds static binaries by default. If you want to build non-static ones use the `-n` flag \(or the alternative `--non-static` flag\).

The `-c` flag tells LDPL to accept source code from the **standard input**.

`-v` and `--version` print out **version** info and release details.

`-h` and `--help` print this list of options.

The `-f` flag can be used to add flags to the C++ compilation line. See the [Building C++ Extensions](../extensions/c++-extensions/building-c++-extensions.md) section for more information.

