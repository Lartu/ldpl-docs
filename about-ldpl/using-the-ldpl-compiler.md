# Using the LDPL Compiler

To use LDPL, you should first download or compile the LDPL compiler.

To use the compiler, you must have a C++ compiler already installed on your system and have mapped it to `c++`, found on your `PATH`. The LDPL Compiler compiles LDPL code to C++ code and thus this is a requirement for it to work.

* **If you want to download a compiled binary:** [download the latest stable release available](https://github.com/Lartu/ldpl/releases). You should then move the binary to a folder on your PATH.
* **If you want to build LDPL yourself:** first, clone this repository. Then `make` and `make install` LDPL in the `src` folder. This will install LDPL and the LDPL documentation \(`man ldpl`\) on your system. LDPL requires only C++11 to compile.

{% hint style="warning" %}
**Note for Windows users:** compilation under Windows has been tested with [MinGW](http://www.mingw.org/wiki/Getting_Started) as installed on that guide. MinGW-w64 seems to have some problems compiling LDPL. Also, it is advised to configure git `autoclrf` to use Unix-style end-of-line: `git config core.autocrlf input`. LDPL relies on an AWK script which will not work properly with DOS-style newlines \(CLRF\).
{% endhint %}

When you are done installing LDPL, write some LDPL source code, say `source.ldpl`. Then compile the source code using `ldpl source.ldpl`. The compiled, executable binary file will be saved as `ldpl-bin`. Done! For more info on the compiler run `ldpl -h`. Example code can be found on [the LDPL website](http://ldpl.lartu.net).

