# Compilador

Este projeto é uma versão resumida da linguagem DL.
Esse projeto faz a análise léxica.
Ela está de acordo com a gramática abaixo.

Gramática
PROGRAM				::= programa ID BLOCK
BLOCK				::= inicio STMTS fim
STMTS				::= STMT; STMTS | ε
STMT				::= BLOCK | DECL | ASSIGN | WRITE | IF
DECL     			::= TYPE ID
ASSIGN   			::= ID = EXPR
WRITE				::= escreva(ID)
IF					::= se (EXPR) STMT
EXPR				::= EXPR "|" REL | REL
REL					::= REL < ARITH | REL <= ARITH | REL > ARITH | ARITH
ARITH  				::= ARITH + TERM | ARITH - TERM | TERM
TERM				::= TERM * FACTOR | FACTOR
FACTOR				::= (EXPR) | ID | LIT_INT | LIT_REAL | LIT_BOOL

Definições Regulares
LETTER		::= a | b | ... | z | A | B | ... Z | _
DIGIT		::= 0 | 1 | ... | 9
ID			::= LETTER (LETTER | DIGIT)*
LIT_INT		::= DIGIT+
LIT_REAL	::= DIGIT+ . DIGIT+ 
LIT_BOOL	::= verdadeiro | falso
TYPE     	::= inteiro | real | booleano
