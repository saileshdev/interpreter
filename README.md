# DSL Interpreter

This is an interpreter written in python which parsers a Domain Specific Language.

## Running locally

```sh
git clone https://github.com/saileshdev/interpreter
cd interpreter/src
python interpreter.py ./../parse/dsl_program
```

## Grammar of the DSL

    compound_statement : BEGIN statement_list END

    statement_list : statement
                   | statement SEMI statement_list

    statement : compound_statement
              | assignment_statement
              | empty

    assignment_statement : variable ASSIGN expr

    empty :

    expr: term ((PLUS | MINUS) term)*

    term: factor ((MUL | DIV) factor)*

    factor : PLUS factor
           | MINUS factor
           | INTEGER
           | LPAREN expr RPAREN
           | variable

    variable: ID


## Sample DSL program

```
BEGIN
    BEGIN
        number := 2;
        a := number;
        b := 10 * a + 10 * number / 4;
        c := a - - b
    END;
    x := 11;
END.
```


