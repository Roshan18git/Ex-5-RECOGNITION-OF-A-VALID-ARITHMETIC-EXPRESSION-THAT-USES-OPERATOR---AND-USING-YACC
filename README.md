# Ex-5-RECOGNITION-OF-A-VALID-ARITHMETIC-EXPRESSION-THAT-USES-OPERATOR-AND-USING-YACC
# Name:Roshan G
# Register No:2122231040176
# Date:
# AIM
To write a yacc program to recognize a valid arithmetic expression that uses operator +,- ,* and /.
# ALGORITHM
1.	Start the program.
2.	Write a program in the vi editor and save it with .l extension.
3.	In the lex program, write the translation rules for the operators =,+,-,*,/ and for the identifier.
4.	Write a program in the vi editor and save it with .y extension.
5.	Compile the lex program with lex compiler to produce output file as lex.yy.c. eg $ lex filename.l
6.	Compile the yacc program with yacc compiler to produce output file as y.tab.c. eg $ yacc –d arith_id.y
7.	Compile these with the C compiler as gcc lex.yy.c y.tab.c
8.	Enter an arithmetic expression as input and the tokens are identified as output.
# PROGRAM
```
%{ 
/* This LEX program returns the tokens for the expression */ 
#include "y.tab.h" 
%} 
%% 
"=" {printf("\n Operator is EQUAL");} 
"+" {printf("\n Operator is PLUS");} 
"-" {printf("\n Operator is MINUS");} 
"/" {printf("\n Operator is DIVISION");} 
"*" {printf("\n Operator is MULTIPLICATION");} 
[a-zA-Z]*[0-9]* { 
printf("\n Identifier is %s",yytext); 
return ID; } 
. return yytext[0]; 
\n return 0; 
%% 
int yywrap() 
{ 
return 1; 
}

```
# OUTPUT
![image](https://github.com/maddyv123/Ex-5-RECOGNITION-OF-A-VALID-ARITHMETIC-EXPRESSION-THAT-USES-OPERATOR---AND-USING-YACC/assets/153618028/1f2b56c7-1ec7-4204-af95-a066406742f1)

# RESULT
A YACC program to recognize a valid arithmetic expression that uses operator +,-,* and / is executed successfully and the output is verified.
