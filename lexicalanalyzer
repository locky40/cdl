%{
#include<stdio.h>
%}
identifier [a-zA-Z][a-zA-Z0-9]*
%%
#.* {printf("\n%s is a preprocessor diirective",yytext);}
int |
float |
char |
double |
while |
for |
struct |
typedef |
do |
if |
break |
continue |
void |
switch |
return |
else |
goto {printf("\n\t%s is a keyword", yytext);}
[\t]*"/*".*"*/"[\t]*\n {printf("\n\t %s is a COMMENT", yytext);}
{identifier}\( {printf("\nFUNCTION \n\t%s", yytext);}
\{ {printf("\n BLOCK BEGINS");}
\} {printf("\nBLOCK ENDS");}
{identifier}(\[[0-9]*\])? {printf("\n %s IDENTFIER",yytext);}
\".*\" {printf("\n\t %s is literal", yytext);}
[0-9]+ {printf("\n \t %s is a NUMBER", yytext);}
= {printf("\n\t %s is an ASSIGNMENT OPERATOR", yytext);}
\+ |
\- |
\* |
\/ |
\% {printf("\n\t %s is an ARITHMETIC OPERATOR", yytext);}
\<= |
\>= |
\< |
== |
\> {printf("\n\t%s is a RELATIONAL OPERATOR",yytext);}
%%
int main(int argc, char **argv)
{
FILE *file;
file=fopen("input.c","r");
if(!file)
{
printf("could not open the file");
exit(0);
}
yyin=file;
yylex();
printf("\n");
return (0);
}
int yywrap()
{
return (1);
}
