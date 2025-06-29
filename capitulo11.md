# Chapter 11 – Code Generation

## 11.1 Introduction

Congratulations, you have made it to the final stage of the compiler! After
scanning and parsing the source code, constructing the AST, performing
type checking, and generating an intermediate representation, we are now
ready to generate some code.

To start, we are going to take a na¨ ıve approach to code generation, in
which we consider each element of the program in isolation. Each ex-
pression and statement will be generated as a standalone unit, without
reference to its neighbors. This is easy and straightforward, but it is con-
servative and will lead to a large amount of non-optimal code. But it will
work, and give you a starting point for thinking about more sophisticated
techniques.

The examples will focus on X86-64 assembly code, but they are not
hard to adapt to ARM and other assembly languages as needed. As with
previous stages, we will define a method for each element of a program.
decl codegenwill generate code for a declaration, calling stmt codegen
for a statement, expr codegenfor an expression, and so on. These rela-
tionships are shown in Figure 11.1.

Once you have learned this basic approach to code generation, you
will be ready for the following chapter, in which we consider more complex
methods for generating more highly optimized code.


