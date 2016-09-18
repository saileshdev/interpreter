# Approach

## Problem statement

1. How to parse and interpret a DSL.
2. How to parse and interpret compound statements.
3. How to parse and interpret assignment statements, including variables.


## DSL rules:

1. The DSL program consists of a compound statement that ends with a dot. Here is an example of a program: “BEGIN  END.”

2. What is a compound statement? A compound statement is a block marked with BEGIN and END that can contain a list (possibly empty) of statements including other compound statements. Every statement inside the compound statement, except for the last one, must terminate with a semicolon. The last statement in the block may or may not have a terminating semicolon. Here are some examples of valid compound statements: “BEGIN END”
“BEGIN a := 5; x := 11 END”
“BEGIN a := 5; x := 11; END”
“BEGIN BEGIN a := 5 END; x := 11 END” 

3. A statement list is a list of zero or more statements inside a compound statement.

4. A statement can be a compound statement, an assignment statement, or it can be an empty statement. 

5. An assignment statement is a variable followed by an ASSIGN token (two characters, ‘:’ and ‘=’) followed by an expression. “a := 11”
“b := a + 9 - 5 * 2” 

6. A variable is an identifier. We’ll use the ID token for variables. The value of the token will be a variable’s name like ‘a’, ‘number’, and so on. In the following code block ‘a’ and ‘b’ are variables: “BEGIN a := 11; b := a + 9 - 5 * 2 END”  7. An empty statement represe nts a grammar rule with no further productions. We use the empty_statement grammar rule to indicate the end of the statement_list in the parser and also to allow for empty compound statements as in ‘BEGIN END’.

8. The factor rule is updated to handle variables.
