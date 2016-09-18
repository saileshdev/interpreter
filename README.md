# DSL Interpreter

This is an interpreter written in python which parsers a Domain Specific Language.

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


