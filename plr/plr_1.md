# Lexical Analysis
## Namen, Schlüsselwörter und Bezeichner
* > NAME tokens represent identifiers, keywords, and soft keywords.

* ```
  NAME: name_start name_continue*
  ```

  * ```
    name_start:    
      | "a"..."z"
      | "A"..."Z"
      | "_"
      | <non-ASCII character>
    ```

  * ```
    name_continue:
      | name_start
      | "0"..."9"
    ```

* ```
  identifier: <NAME, except keywords>
  ```

* **keywords**:
  |          |            |           |            |          |
  | -------- | ---------- | --------- | ---------- | -------- |
  | `False`  | `await`    | `else`    | `import`   | `pass`   |
  | `None`   | `break`    | `except`  | `in`       | `raise`  |
  | `True`   | `class`    | `finally` | `is`       | `return` |
  | `and`    | `continue` | `for`     | `lambda`   | `try`    |
  | `as`     | `def`      | `from`    | `nonlocal` | `while`  |
  | `assert` | `del`      | `global`  | `not`      | `with`   |
  | `async`  | `elif`     | `if`      | `or`       | `yield`  |

## Literale
* > Literals are notations for constant values of some built-in types.


* ```text
  literal:
   | stringliteral
   | bytesliteral
   | NUMBER
  ```

  * ```
    NUMBER:
      | integer
      | floatnumber
      | imagnumber
    ```

* > Other “literals” are lexically denoted using keywords (`None`, `True`, `False`) and the special ellipsis token (`...`).


## Operationen und Trennzeichen

* ```text
  OP:
   | assignment_operator
   | bitwise_operator
   | comparison_operator
   | enclosing_delimiter
   | other_delimiter
   | arithmetic_operator
   | "..."
   | other_op
  ```

  * ```text
    assignment_operator:
      | "+=" | "-=" | "*=" | "**="
      | "%=" | "&=" | "|=" | "^=" | "<<=" | ">>="
      | "@=" | ":=" | "/=" | "//="
    ```

  * ```text
    bitwise_operator:
      | "&" | "|" | "^" | "~" | "<<" | ">>"
    ```

  * ```text
    comparison_operator:
      | "<=" | ">=" | "<" | ">" | "==" | "!="
    ```

  * ```text
    enclosing_delimiter:
      | "(" | ")" | "[" | "]" | "{" | "}"
    ```

  * ```text
    other_delimiter:
      | "," | ":" | "!" | ";" | "=" | "->"
    ```

  * ```text
    arithmetic_operator:
      | "+" | "-" | "**" | "*" | "//" | "/" | "%"
    ```

  * ```text
    other_op: "." | "@"
    ```

* > Some of Python’s operators, like `and`, `or`, and `not in`, use keyword tokens rather than “symbols” (operator tokens).
