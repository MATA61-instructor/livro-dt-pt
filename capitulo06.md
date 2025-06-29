# Chapter 6 – The Abstract Syntax Tree

## 6.1 Overview

The **abstract syntax tree (AST)** is an important internal data structure that
represents the primary structure of a program. The AST is the starting
point for semantic analysis of a program. It is “abstract” in the sense that
the structure leaves out the particular details of parsing: the AST does
not care whether a language has prefix, postfix, or infix expressions. (In
fact, the AST we describe here can be used to represent most procedural
languages.)

For our project compiler, we will define an AST in terms of five C
structures representing declarations, statements, expressions, types, and
parameters. While you have certainly encountered each of these terms
while learning programming, they are not always used precisely in practice.
This chapter will help you to sort those items out very clearly:

- A **declaration** states the name, type, and value of a symbol so that
it can be used in the program. Symbols include items such as 
constants, variables, and functions.

- A **statement** indicates an action to be carried out that changes the
state of the program. Examples include loops, conditionals, and
function returns.

- An **expression** is a combination of values and operations that is
evaluated according to specific rules and yields a value such as an 
integer, floating point, or string. 
In some programming languages, an expression may also have a side effect 
that changes the state of the program.

For each kind of element in the AST, we will give an example of the
code and how it is constructed. Because each of these structures 
potentially has pointers to each of the other types, it is necessary 
to preview all of them before seeing how they work together.

Once you understand all of the elements of the AST, we finish the chap-
ter by demonstrating how the entire structure can be created automatically
through the use of the Bison parser generator.


## 6.2 Declarations

## 6.3 Statements

## 6.4 Expressions

## 6.5 Types

## 6.6 Putting it All Together

## 6.7 Building the AST

## 6.8 Exercises




