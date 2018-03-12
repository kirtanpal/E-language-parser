# E-language-parser

The E programming language is similar to C, C++, Java, Pascal, and Modula-2, but it differs syntactically and semantically, and is considerably simpler.
  This Java program translates E programs to their semantically equivalent C programs. That is, the input to the program (henceforth, the translator) is an E program; the output from the program is a C program (henceforth, the generated code, or simply GC). To verify that the translator works correctly, it is compiled and executed in the GC. As the translator reads a token or a small group of tokens in the E program, it will determine if the token(s) is syntactically and semantically valid, and generate code for the token(s).


The following grammar partially describes the E language. In the EBNF below, nonterminals are in lowercase; terminal symbols are enclosed in single quotes to avoid potential confusion in the use of characters that are both meta-symbols in the grammar and terminals in E, e.g., “[”

 program ::= block
 
 block ::= declaration_list statement_list
 
 declaration_list ::= {declaration}
 
 statement_list ::= {statement}
 
 declaration ::= ’@’ id { ’,’ id }
 
 statement ::= assignment | print | do | if
 
 print ::= ’!’ expr
 
 assignment ::= ref_id ’=’ expr
 
 ref_id ::= [ ’ ̃’ [ number ] ] id
 
 do ::= ’<’ guarded_command ’>’
 
 if ::= ’[’ guarded_command { ’|’ guarded_command } [ ’%’ block ] ’]’
 
 guarded_command ::= expr ’:’ block
 
 expr ::= term { addop term }
 
 term ::= factor { multop factor }
 
 factor ::= ’(’ expr ’)’ | ref_id | number
 
 addop ::= ’+’ | ’-’
 
 multop ::= ’*’ | ’/’
 



 
