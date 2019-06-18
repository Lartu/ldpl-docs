# Data Types

LDPL natively supports the **NUMBER** and **TEXT** data types. It also supports **VECTORS** of values of such types.

The **NUMBER** data type, as its name suggests, depicts numeric values. It's recommended that it be represented internally as a **binary64** double-precision floating-point format number as defined by the **IEEE 754**.

Both variables and numeric constants can be members of the NUMBER type.

Valid number literals must begin with a decimal value \(for example `5` or `0.12`, `.12` wouldn't be a valid NUMBER\) and may be preceded by a minus sign for negative numbers \(`-5`, `-567.912`\). Numbers may not be preceded by a plus sign \(`+5` is not a valid number literal\). The literal `-0` is implicitly transformed into `0`.

The **TEXT** data type, as its name suggests, represents alphanumeric strings. In the interest of supporting as many locales as possible, LDPL should be **utf-8** encoded to be compatible with Unicode. A TEXT maximum length is explicitly not defined and it should be limited only by the amount of available memory on the system. Strings in LDPL are enclosed between two `"`quotes`"` and can contain [multiple escape sequences](https://ldpl.lartu.net/reference/#esc).

Both variables and string constants can be members of the TEXT type.

The **LIST** data type is a collection of NUMBER or TEXT values. Values can be pushed to LISTs and then accessed and modified using the `:` operator. LIST indexes consist of integer numbers. The first index of a LIST is index 0, and the rest count up to the length of the list minus one. LISTs are explained in greater detail in the '[Declaring LIST Variables](../../variables-in-ldpl/declaring-list-variables.md)' section.

LISTs, as collections of NUMBER or TEXT values, can only have one defined type at any given time: TEXT or NUMBER. A single LIST is not capable of storing both numeric and alphanumeric values.

The **MAP** data type is a collection of NUMBER or TEXT values. MAPs superficially resemble LISTs but with fundamental differences. The biggest one is that any number or string in LDPL may be used as an array index, not just consecutive integers. Also, values in MAPs have no order, so there's no one coming before or after any other. MAPs are explained in greater detail in the '[Declaring MAP Variables](../../variables-in-ldpl/usage-of-vectors.md)' section.

MAPs, as collections of NUMBER or TEXT values, can only have one defined type at any given time: TEXT or NUMBER. A single MAP is not capable of storing both numeric and alphanumeric values.

