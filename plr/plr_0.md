# Grundlegender Ablauf
## Tokenization
* Erledigt vom **Lexical Analyzer (Lexer, Tokenizer)**
* > The lexical analyzer determines the program text’s encoding (`UTF-8` by default), and decodes the text into source characters. If the text cannot be decoded, a `SyntaxError` is raised.
* Source characters are then used to generate a stream of `tokens`.

## Parsing
* Erledigt vom **Syntactic Analyzer (Parser)**.
* Dieser erhält stream of `tokens` als Eingabe,
* prüft die Python-Syntax und
* erstellt den **Abstract Syntax Tree (AST)**.

## Compilation
* Bytecode wird erstellt.
* ...

## Execution
* Bytecode wird von `Python Virtual Machine` ausgeführt.
* ...
