**CUCU Compiler**
**G.Varsha-2022csb1082**

**Introduction:**

CUCU (A Compiler U Can Understand) is a toy compiler designed for a simplified subset of the C programming language. This compiler aims to demonstrate the basics of lexing, parsing, and generating output for a small C-like language called CUCU.

**Language Description:**

CUCU supports a limited set of features and constructs inspired by C. Here are the key aspects of the CUCU language:

- **Variables**: Declarations for variables support `int` and `char*` data types.
- **Functions**: Function declarations and definitions are supported, including arguments and return types.
- **Statements**: CUCU supports various types of statements, including assignment, function calls, return statements, and control statements (if-else and while).
- **Expressions**: Arithmetic and Boolean expressions are supported, including basic operators such as addition, subtraction, multiplication, division, and comparison operators.
- **Comments**: Comments can be enclosed within `/* */`.

**Lexer Output:**

The lexer produces tokenized output indicating the type of each token along with its value. Lexical errors are reported using `yyerror` and displayed in the `Lexer.txt` file.

**Parser Output:**

The parser generates a structured output in `Parser.txt`, listing all successfully parsed terminals, non-terminals, expressions, and statements from the source code. Syntactical errors are reported using `yyerror` and displayed in the Parser.txt file.

**Compiling and Running:**

To compile and run the CUCU compiler, follow these steps:

1. Ensure you have the necessary files (cucu.l, cucu.y, input.cu) in the same directory.
2. Compile the lexer and parser using the following command:

   ```
   flex cucu.l
   yacc -d cucu.y
   gcc lex.yy.c y.tab.c -o cucu -lfl
   ```

3. Run the compiler with a CUCU source file as input:

   ```
   ./cucu input.cu
   ```

   Replace `input.cu` with the name of your CUCU source file.

**Sample Input and Output:**

I have included two sample files:

`Sample1.cu`: Contains sample CUCU code with correct syntax.
`Sample2.cu`: Contains sample CUCU code with incorrect syntax.
Running the compiler on these sample files demonstrates its ability to recognize correct and incorrect syntax, producing appropriate lexer and parser outputs.

**Assumptions:**

1. Function and variable names consist of letters, digits, and underscores, starting with a letter.
2. Boolean expressions are limited to relational operators `==` and `!=`.
3. Precedence order for operators: Parenthesis, `*` and `/`, `+` and `-`, `==` and `!=`, assignment (`=`).
4. Nested comments are not supported.
5. All if-else control statements are of the form `if (condition) { statement } else { statement }`.
