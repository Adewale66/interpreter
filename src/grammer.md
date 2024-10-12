```
program        → statement* EOF ;
declaration    → varDecl | statement ;
varDecl        → "var" IDENTIFIER ( "=" expression )? ";" ;
statement      → exprStmt | forStmt | ifStmt | printStmt | whileStmt | block ;
forStmt        → "for" "(" ( varDecl | exprStmt | ";" ) expression? ";" expression? ")" statement ;
whileStmt      → "while" "(" expression ")" statement ;
ifStmt         → "if" "(" expression ")" statement ( "else" statement )? ;
block          → "{" declaration* "}" ;
exprStmt       → expression ";" ;
printStmt      → "print" expression ";" ;
expression     → equality ;
assignment     → IDENTIFIER "=" assignment | equality ;
equality       → comparison ( ( "!=" | "==" ) comparison )* ;
comparison     → term ( ( ">" | ">=" | "<" | "<=" ) term )* ;
term           → factor ( ( "-" | "+" ) factor )* ;
factor         → unary ( ( "/" | "*" ) unary )* ;
unary          → ( "!" | "-" ) unary | primary ;
primary        → NUMBER | STRING | "true" | "false" | "nil" | "(" expression ")" | IDENTIFIER ;
```