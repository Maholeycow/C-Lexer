# C-Lexer
Lexer (Scanner) that goes over CCX files
This is a school assignment that is a 7 week project.
The purpose of this repository is to help me with the development of this project as I will be developing this lexer piece by piece.
See the details below of what the lexer does.

Modern translation systems often use lexical analysis to divide an input into meaningful units. Oncethesemeaningfulunits(orlexemesortokens) have been derived, other components within the translation system are used to determine the relationships among the lexemes. Lexical analyzers (or lexers) are commonly used in compilers, interpreters, and other translation systems that you have often used. The act of lexical analysis is also known as scanning.
For this assignment you are to build a lexer that will successfully scan through a set of programs expressed in the CCX programming language. You have never used CCX, and that is just ﬁne: scanning through CCX programs won’t require intimate knowledge of CCX.
Your lexer shall be written in the C programming language. You may not use C++. Your lexer will be compiled and tested using gcc on the wormulon server, so you should at least test your lexerinthissameenvironment. You are expressly forbidden from using any standard template library (STL) containers (e.g. <vector>), algorithms (via <algorithm>), or other facilities in your lexer. You may not use any lexer generators or other automated tools to complete this assignment.

------------------------------------------------------------------------------------------
Cool, right? Now I will show you what we will be looking for below:

As mentioned, your lexer shall classify each lexeme encountered into one of 8 categories. The details of each category follow.
• comment Comments in CCX begin with /∗ and end with ∗/ (C-style comments). Comments can span multiple lines. Everything encountered between (and including) the /∗ and ∗/ delimiters is considered part of the comment lexeme.
• identifier Identiﬁers are used in programs to name entities such as variables. Every programming language has its own rules as to what constitutes a legal identiﬁer. In CCX an identiﬁer can be composed of letters, digits, and underscores, but must start with a letter. You may assume that your lexer will never encounter an identiﬁer that is more than 256 characters long.
• string Strings in CCX are literals delimited by double-quotes ”like this”. The double-quotes are part of the lexeme. When you print a lexeme that has been classiﬁed as a string, you must print the double-quotes. You may assume that your lexer will never encounter a string that is more than 256 characters long.
• keyword CCX contains many keywords. Keywords are sometimes called reserved words. Keywords (like all of CCX) are case-sensitive, and may not be used as identiﬁers in legal programs. It is not the job of the lexer to determine whether a keyword is misused; the lexer simply classiﬁes a particular lexeme as being a keyword. The following are the list of CCX keywords that your lexer must recognize:
accessor and array begin bool case else elsif end exit function if in integer interface is loop module mutator natural null of or others out positive procedure return struct subtype then type when while
• character literal Character literals in CCX are literals in single-quotes like this: ’x’. CCX allows character escape sequences in character literals, such as ’\020’ but your lexer need not support this.
• operator CCX contains many operators. Some operators consist of a single character, whereas others contain multiple characters. The following is a list of the operators that your lexer must recognize. Each operator is enclosed in double-quotes for the purpose of disambiguation, but these double-quotes are not part of the operator:
"." "<" ">" "(" ")" "+" "-" "*" "/" "|" "&" ";" "," ":" "[" "]" "=" ":=" ".." "<<" ">>" "<>" "<=" ">=" "**" "!=" "=>"
• numeric literal CCX allows numeric literals in multiple forms. Your lexer will recognize a simpliﬁed subset of CCX numeric literals. Each numeric literal encountered by your lexer will start with a decimal digit and will contain only the following:
– decimal digits (0 through 9) – hexadecimal digits (A through F and/or a through f) – the special characters ’ ’, ’.’, and ’#’.
any other character encountered will denote that the numeric literal has ended and a new lexeme has begun.
• UNK This special category is set aside for lexemes that your lexer cannot classify, and is intended to assist you in building and debugging your lexer. This category is composed of all lexemes that do not ﬁt in any of the other speciﬁed categories. Your lexer will only be tested against legal CCX programs, so if the logic in your lexer is correct, you should never encounter an UNK lexeme. If, however, your lexer does encounter a lexeme that does not ﬁt the requirements of any of the other categories, your lexer must print the offending lexeme, along with its category name in parenthesis, and immediately terminate
