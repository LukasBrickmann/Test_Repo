# Syntactic Analysis
## Atom
```text
atom:
  | builtin_constant
  | identifier
  | literal
  | parenthesized_enclosure
  | bracketed_enclosure
  | braced_enclosure
```
* ```text
  builtin_constant:
    | 'True'
    | 'False'
    | 'None'
    | '...'
  ```

* ```text
  parenthesized_enclosure:
     | group
     | tuple
     | yield_atom
     | generator_expression
  ```

* ```text
  bracketed_enclosure:
     | listcomp
     | list
  ```

* ```text
  braced_enclosure:
     | dictcomp
     | dict
     | setcomp
     | set
  ```

## Primary
```
primary:
  | atom | attributeref | subscription | call
```

## Power
```
power: (await_expr | primary) ["**" u_expr]
```

* ```
  await_expr: "await" primary
  ```

## Unary operations
```
u_expr:
  | power
  | "-" u_expr
  | "+" u_expr
  | "~" u_expr
```

## Binary arithmetic operations
```
m_expr:
  | u_expr
  | m_expr "*" u_expr
  | m_expr "@" m_expr
  | m_expr "//" u_expr
  | m_expr "/" u_expr
  | m_expr "%" u_expr
```

```
a_expr:
  | m_expr
  | a_expr "+" m_expr
  | a_expr "-" m_expr
```

## Binary bitwise operations
```
and_expr:
  | shift_expr
  | and_expr "&" shift_expr
```

* ```
  shift_expr:
    | a_expr
    | shift_expr ("<<" | ">>") a_expr
  ```

```
xor_expr:
  | and_expr
  | xor_expr "^" and_expr
```

```
or_expr:
  | xor_expr
  | or_expr "|" xor_expr
```

## Comparisons
```
comparison: or_expr (comp_operator or_expr)*
```

```
comp_operator:
  | "<"
  | ">"
  | "=="
  | ">="
  | "<="
  | "!="
  | "is" ["not"]
  | ["not"] "in"
```

## Boolean operations
```
or_test:
  | and_test
  | or_test "or" and_test
```

```
and_test:
  | not_test
  | and_test "and" not_test
```

```
not_test:
  | comparison
  | "not" not_test
```

## Expression
```
expression:
  | conditional_expression
  | lambda_expr
```

* ```
  conditional_expression:
    or_test ["if" or_test "else" expression]
  ```

* ```
  lambda_expr:
    "lambda" [parameter_list] ":" expression
  ```

## Flexible Expression
```
flexible_expression:
  | assignment_expression
  | starred_expression
```
* ```
  starred_expression:
    | "*" or_expr
    | expression
  ```
* ```
  assignment_expression: [identifier ":="] expression
  ```

## Comprehension
```
comprehension: flexible_expression for_if_clause+
```

```
for_if_clause:
   | ['async'] 'for' target_list 'in' or_test ('if' or_test)*
```

* ```
  target_list: target ("," target)* [","]
  ```

  * ```
    target:
      | identifier
      | "(" [target_list] ")"
      | "[" [target_list] "]"
      | attributeref
      | subscription
      | "*" target
    ```

### Generator, listcomp, setcomp, dictcomp
```
generator_expression: "(" comprehension ")"
```

## Expression lists

```
flexible_expression_list:
  | flexible_expression ("," flexible_expression)* [","]
```

```
starred_expression_list:
  | starred_expression ("," starred_expression)* [","]
```

```
expression_list:
  | expression ("," expression)* [","]
```

```
yield_list:
  | expression_list
  | starred_expression "," [starred_expression_list]
```

## Lists, Sets, Dictionaries
```
list: '[' [flexible_expression_list] ']'
```
```
listcomp: '[' comprehension ']'
```

```
set: '{' flexible_expression_list '}'
```
```
setcomp: '{' comprehension '}'
```

```
dict: '{' [double_starred_kvpairs] '}'
```
* ```
  double_starred_kvpairs: ','.double_starred_kvpair+ [',']
  double_starred_kvpair: '**' or_expr | kvpair
  kvpair: expression ':' expression
  ```

```
dictcomp:
  | '{' kvpair for_if_clause+ '}'
  | '{' '**' expression for_if_clause+ '}'
```

## Yield Atom
```
yield_atom: "(" yield_expression ")"

```

* ```
  yield_expression: "yield" yield_list | yield_from
  ```

* ```
  yield_from: "yield" "from" expression
  ```
