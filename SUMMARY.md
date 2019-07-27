# Table of contents

* [Introduction](README.md)
* [About LDPL](about-ldpl/README.md)
  * [File Extensions](about-ldpl/file-extensions.md)
  * [Using the LDPL Compiler](about-ldpl/using-the-ldpl-compiler.md)
  * [LDPL Compiler Switches](about-ldpl/ldpl-compiler-options.md)
* [Structure of LDPL Source Code](structure-of-ldpl-source-code/README.md)
  * [Comments in LDPL](structure-of-ldpl-source-code/comments-in-ldpl.md)
  * [DATA Section](structure-of-ldpl-source-code/data-section/README.md)
    * [Data Types](structure-of-ldpl-source-code/data-section/data-types.md)
  * [PROCEDURE Section](structure-of-ldpl-source-code/procedure-section.md)
  * [SUB-PROCEDUREs](structure-of-ldpl-source-code/sub-procedures.md)
  * [Importing other sources](structure-of-ldpl-source-code/importing-other-sources.md)
* [Variables in LDPL](variables-in-ldpl/README.md)
  * [Declaring LIST Variables](variables-in-ldpl/declaring-list-variables.md)
  * [Declaring MAP variables](variables-in-ldpl/usage-of-vectors.md)
  * [Default Variable Values](variables-in-ldpl/default-variable-values.md)
  * [Command Line Arguments](variables-in-ldpl/command-line-arguments.md)
  * [ERRORCODE and ERRORTEXT](variables-in-ldpl/errorcode-and-errortext.md)
  * [Escape Sequences](variables-in-ldpl/escape-sequences.md)
* [Identifier Naming Schemes](naming-rules.md)

## Control Flow Statements

* [STORE - IN](control-flow-statements/store-in.md)
* [IF - IS - THEN](control-flow-statements/if-is-then/README.md)
  * [ELSE IF - IS - THEN](control-flow-statements/if-is-then/else-if-is-then.md)
* [WHILE - IS - DO](control-flow-statements/while-is-do.md)
* [FOR - FROM - TO - STEP - DO](control-flow-statements/for-from-to-step-do.md)
* [FOR EACH - IN - DO](control-flow-statements/for-each-in-do.md)
* [BREAK](control-flow-statements/break.md)
* [CONTINUE](control-flow-statements/continue.md)
* [CALL SUB-PROCEDURE](control-flow-statements/call-sub-procedure.md)
* [RETURN](control-flow-statements/return.md)
* [EXIT](control-flow-statements/exit.md)
* [WAIT - MILLISECONDS](control-flow-statements/wait-milliseconds.md)
* [GOTO & LABEL](control-flow-statements/goto-and-label.md)
* [CREATE STATEMENT - EXECUTING](control-flow-statements/create-statement-executing.md)

## Arithmetic Statements

* [IN - SOLVE](arithmetic-statements/in-solve.md)
* [FLOOR](arithmetic-statements/floor.md)
* [MODULO - BY - IN](arithmetic-statements/modulo-by-in.md)
* [GET RANDOM IN](arithmetic-statements/store-random-in.md)

## Text Statements

* [JOIN - AND - IN](text-statements/join-and-in.md)
* [REPLACE - FROM - WITH - IN](text-statements/replace-from-with-in.md)
* [SPLIT - BY - IN](text-statements/split-by-in.md)
* [GET CHARACTER AT - FROM - IN](text-statements/get-character-at-from-in.md)
* [GET LENGTH OF - IN](text-statements/store-length-of-in.md)
* [GET ASCII CHARACTER - IN](text-statements/store-character-in.md)
* [GET CHARACTER CODE OF - IN](text-statements/store-character-code-of-in.md)
* [STORE QUOTE - IN](text-statements/store-quote-in.md)
* [IN - JOIN](text-statements/in-join.md)
* [GET INDEX OF - FROM - IN](text-statements/get-index-of-from-in.md)
* [COUNT - FROM - IN](text-statements/count-from-in.md)
* [SUBSTRING - FROM - LENGTH - IN](text-statements/substring.md)
* [TRIM - IN](text-statements/trim-in.md)

## LIST Statements

* [PUSH - TO](list-statements/push-to.md)
* [CLEAR](list-statements/clear.md)
* [COPY - TO](list-statements/copy-to.md)
* [GET LENGTH OF - IN](list-statements/store-length-of-in.md)
* [DELETE LAST ELEMENT OF](list-statements/delete-last-element-of.md)

## MAP STATEMENTS <a id="vector-statements"></a>

* [CLEAR](vector-statements/clear.md)
* [COPY - TO](vector-statements/copy-to.md)
* [GET KEY COUNT OF - IN](vector-statements/store-index-count-of-in.md)
* [GET KEYS OF - IN](vector-statements/store-indices-of-in.md)

## I/O Statements

* [DISPLAY](i-o-statements/display.md)
* [ACCEPT](i-o-statements/accept.md)
* [EXECUTE](i-o-statements/execute.md)
* [EXECUTE - AND STORE OUTPUT IN](i-o-statements/execute-and-store-output-in.md)
* [EXECUTE - AND STORE EXIT CODE IN](i-o-statements/execute-and-store-exit-code-in.md)
* [ACCEPT - UNTIL EOF](i-o-statements/accept-until-eof.md)
* [LOAD FILE - IN](i-o-statements/load-file-in.md)
* [WRITE - TO FILE](i-o-statements/write-to-file.md)
* [APPEND - TO FILE](i-o-statements/append-to-file.md)

## Extensions

* [C++ Extensions](extensions/c++-extensions/README.md)
  * [Writing C++ Extensions](extensions/c++-extensions/writing-c++-extensions.md)
  * [Building C++ Extensions](extensions/c++-extensions/building-c++-extensions.md)
  * [External Identifier Naming Scheme](extensions/c++-extensions/external-identifier-naming-scheme.md)
  * ["Hello World" C++ Example](extensions/c++-extensions/hello-world-c++-example.md)
  * [More Examples](extensions/c++-extensions/more-examples.md)
* [CALL EXTERNAL](extensions/call-external.md)
* [EXTERNAL SUB-PROCEDUREs](extensions/external-sub-procedures.md)
* [EXTERNAL Variables](extensions/external-variables.md)

